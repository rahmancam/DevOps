# DevOps
 ## DevOps Approach
  - Best suited when:
    - Requirements change frequently
    - Development needs to be Agile
    - Operations needs to be Agile

### Facebook Challenges 2011
    - Features released to 500 million users
    - Heavy website traffic
    - Server meltdown
    - Mixed responses from users which leads to no conclusion
 #### Dark Launching Technique
    - The new features are first deployed on a smaller & specific user base(zone)
    - They are continuously monitored and the feedbacks are continuously developed and tested
    - Once the features are stable, they are deployed on other user bases in multiple releases
    To implement Dark launching, the below activities are fundamental as they lie at the heart of the DevOps lifecycle:
    - Continous Development
    - Continuous Testing
    - Continuous Integration
    - Continuous Deployment
    - Continuous Monitoring
    Plan->Code->Build->Test->Deploy->Operate->Monitor->Plan->Code->.....

### Continuous Devlopment (Phase 1 - Plan & Code)
  - Involves planning and coding of the software application functionality.
  - The vision of the project is decided during planning phase
  - Code can be done in any language but maintain by Version Control System

  #### Why Code Versioning is important ?
  - Versions are maintained to hold a single source of application
  - Using centralized single source code, Operations can access the same code what what they plan to release
  - Easy to Rollout the faulty snippet of code or complete release.

### Continuous Testing (Phase 2 - Build & Test)
  - Unit tests
### Contnuous Integration (Phase 3)
  - CI is process of Automated Build and Automated tests
  - It helps to detect error quickly and locate them easily.
  - Its not about resolve the bug but to find them more quickly.
  - It increase visibility enabling greater communications
  - Catch issues at earlier stages
  - Spend less time debugging and more time adding features
  - Stop waiting to find out if your code's going to work
  - Reduce integration problems allowing you to deliver software

### Continuous Deployment
  - CD is related CI and refers to keeping your application deployable at any point
  - With the help of CD you can deploy application latest version to Test or Production environment
### Continuous Delivery
  - It is the practice of keeping your codebase deployable at any point. Beyond making sure your application passes automated tests it has to have all the configurations necessary to push it into production.

### Continuous Deployment and Continuous Monitoring
  - Continuous Deployment
    - Configuration Management
      - Establish and maintain application's functional requirements and performance
      - Releasing deployments to Servers
      - Scheduling updates on all servers
      - Maintain Configuration consistency on all servers
    - Containerization
      - It is a set of tools which will maintain the consistency across environments
      - Docker is the first containerization tool
      - Scheduling updates on all servers
      - Maintain configuration consistency on All servers
    - Continuous Monitoring
      - Monitor the system performance
      - Monitor the Product's overall performance

## Jenkins
  - Continuous integration (CI) is a development practice that requires developers to integrate code into a shared repository several times a day.
  - Each check-in is then verified by an automated build, allowing teams to detect problems early.
  - If build is not Green, system notify developers immediately. By this, developer can detect errors quickly, and locate them more easily
  - Why do we need CI ?
    - Less back-tracking to discover where things went wrong
    - CI is cheap, if you don't follow a continuous approach, you'll have longer periods between integrations. This makes it exponentially more difficult to find and fix problems.
  ### Stages of adopting continuous integration
    - Continuous integration is backed by several important principles and practices
    - The practice
      - maintain a single source repository
      - automate the build and execute tests
      - make your build self-testing.
      - make it easy for anyone to get the latest executable version.
      - everyone can see what's happening.
      - automate deployment.
    - How to do it
      - Developers checkout code into their own workspaces
      - When done, commit the changes to the repository
      - CI server monitors the repository and checks out changes when they occur
      - CI server builds the system and runs unit and integration tests
      - CI server releases `deployable artifacts` for testing
      - CI server assigns a `build label` to the version of the code it just built
      - if the build or tests fail, the CI server alerts the team.
      - The team fixes the issue at the earliest opportunity
      Teams Responsibility
        - Check in frequently
        - Don't check in broken code
        - Don't check in untested code
        - Don't check in when the build is broken
      - CI is the practice of merging stable development work branch with the main branch constantly
     Continuous Delivery
      - Continuous delivery of code to an environment once the code is ready to ship.
      - Environment could be staging or production. First product is deliver to QAs and Review before shipping to Customer/ Production
    Continuous Deployment
      - Essentialy, it is the practice of releasing every good build to users
      - The deployment of Product in Production as soon as it's ready.

      - By adopting both continuous integration and continuous deployment, you not only reduce risks and catch bugs quickly, but also move rapidly to working software.

  ## Jenkins
    - Open source CI/CD tool written in Java.
    - It is an automated tools, used to build and deliver the software product.
    - Jenkins was forked from another project called Hudson, after dispute with Oracle,
    - It is a server-based application and requires a web server like Apache Tomcat.
    - It became popular because of its monitoring of repeated tasks which arise during the development of a project
    - Why use Jenkins for CI ?
      - Code is built and test as soon as developer commits code. Jenkins will build and test code many times during the day.
      - On successful build, Jenkins will deploy the source into the test server and notifies the deployment team.
      - On build failures, Jenkis will notify the errors to the developer team 
      - Jenkins also supports cloud-based architecture so that you can deploy jenkins in cloud-based platforms
      - Jenkins support Docker containers, you can containerize Jenkins service
    - Jenkins Alternatives
      - Drone CI (Written in GO)
      - TeamCity (JetBrains)
      - Wrecker
      - CircleCI
      - CodeShip
      - SemaPhoreCI
  - Architecture
    - Master:
      - Schedules Build Job
      - Dispatches builds to the slave for actual job execution
      - Monitoring the slave and recording the build results

    - Slave:
      - Execute build jobs dispatched my master
      - Jenkins Job:
        - Job is refer to runnable tasks that are controlled and monitored by Jenkins
      - Slave/ Node:
        - Slaves are computers that are setup to build Projects for a master
        - Jenkins Run separate program called 'Slave agents' on Slaves.
        - When slaves are registered to a master, a master starts distributing the load to Slaves.
      




