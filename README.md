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
    

## Contribute

You are very much welcome to contribute on this repo, you can open an issue or PR for contributing on this repo. 

# Resources 

- [DevOps CI/CD Explained in 100 Seconds](https://www.youtube.com/watch?v=scEDHsr3APg)
- [What is CI CD | What is CI CD Pipeline | Interview questions](https://www.youtube.com/watch?v=k2aNsQKwyOo)

