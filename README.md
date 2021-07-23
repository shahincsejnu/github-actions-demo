# github-actions-demo

This repository contains the stuffs related to GitHub Actions. I just recently start learning/exploring about github actions, this repo is to track things that I learn or go through during this learning period.

## CI/CD Basics

* CI : Continuous Integration : 
    * automating the repetitive works by running a workflow in CI server (pre set) on every(or choosed) commit in respective git repo.
    * commit changes --> git repo --> CI server --> Success/Fail.
    * through CI/CD issues (small!) can be detected before merging them into the master.
    * developer gets feedback about the tests
    * can find bugs early and fix them
    * deploy often, and deliver faster as the code is tested
    * to check whether the build and tests is success/fail
    
* CD : Continuous Deployment/Delivery : 
    * Because of CI we can ensure the software can be released reliably
    * So the deployments/delivery happen often and quick
    * Automated deployment
    
* Tools :
    - CodeDeploy
    - Jenkins CD
    - Spinnaker
    - GitHub Actions
    - Etc...
    
* Continuous Delivery vs Continuous Deployment :
    - Both are automated, both run automation tests to ensure the build is ready for release, ensures the build is always in a deployable state
    - In Continuous Delivery, may involve a manual step to 'approve' a deployment
    - In Continuous Deployment no manual intervention of approvals, full automation.

* CI/CD Pipeline :
    - all the above process of CI and CD are integrated with each other, they have automated triggers, when first process is completed and pass then it will trigger the next one, these automated triggered processes are chained together, and it is call CI/CD pipeline.

* Summary :
  <figure align="center">
    <img alt="CI/CD Summary" src="/images/ci-cd-summary.png">
    <figcaption align="center">Fig: CI/CD Summary</figcaption>
  </figure>
    

## GH Actions

- GH Actions is a platform to automate software developers workflows
- CI/CD is one of many workflows, though some refers GH actions is a CI/CD platform  
- CI/CD pipeline with GitHub Actions
- GH Actions lets us run shell commands against our repo code using GH's cloud infrastructure and is triggered on an event, like a commit, a PR or on a schedule.
- GitHub Actions is a free service which can run on a repo if it's configured
- It basically works as a CI server.
- It's structure is like :
  - `.github/workflows/` in this folder we can add github actions workflows, which are basically yaml file, where we define the respective GH actions
- Concepts :
  - Workflow :
    - actions config is a 'workflow' of tiggers and steps
    - a workflow is a yaml file in `.github/workflows/` folder, ex : `.github/workflows/main.yml`
  - Job :
    - the job is the what actually executes
    - a workflow can consist of one or more jobs
    - if we define more than one job then by default all jobs run in parallel, but if we have any dependency then we need to overwrite the default value by `needs: <name_of_the_parent_job>` inside a job
  - Runner :
  
  - Events :

- Self Hosted Runner :
  - we can use a self hosted runner (third-party) as CI server instead of github hosted runners, the server will listen to jobs (push to branch, as specified) and then it will do the steps
  - To use this see [doc](https://docs.github.com/en/actions/hosting-your-own-runners/about-self-hosted-runners) for details
  - for setting up self hosted runners see [doc](https://docs.github.com/en/actions/hosting-your-own-runners/adding-self-hosted-runners)
  - Warning: We recommend that you only use self-hosted runners with private repositories. This is because forks of your repository can potentially run dangerous code on your self-hosted runner machine by creating a pull request that executes the code in a workflow.

- Benefits of GitHub Actions:
  - CI/CD with github actions
  - use same tool (github) instead of another third-party CI/CD tool to integrate in github
  - setup the pipeline is easy
  

## Demo (Create a simple GH Action)

You can create GH Action in two ways : 

1. one is by clicking the Actions tab and following the instructions : 
    - choose a github repo
    - Click the `Actions` tab on your repo
    - go for simple workflow (or any other given workflows as your need), then just change the `yml` file as your need
2. by adding yaml files (containing the github actions code) in `.github/workflows/` folder, like :
    - `.github/workflows/main.yml` : 
      - ```yaml
        name: CI
        
        on: push
        
        jobs:
          build:
          runs-on: ubuntu-latest
          
              steps:
                - uses: actions/checkout@v2
          
                - name: Run a one-line script
                  run: echo "Hello, world!"
        ```

# Contribute

You are very much welcome to contribute on this repo, you can open an issue or PR for contributing on this repo. 

# Resources 

- [DevOps CI/CD Explained in 100 Seconds](https://www.youtube.com/watch?v=scEDHsr3APg)
- [What is CI CD | What is CI CD Pipeline | Interview questions](https://www.youtube.com/watch?v=k2aNsQKwyOo)
- [Getting Started with GitHub Actions](https://www.youtube.com/watch?v=KUxg-7U9EKM)
- [Example](https://dev.to/michaelcurrin/intro-tutorial-to-ci-cd-with-github-actions-2ba8)
- [GitHub Actions Tutorial - Basic Concepts and CI/CD Pipeline with Docker](https://www.youtube.com/watch?v=R8_veQiYBjI)

