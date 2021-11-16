# alone-ci-cd
CI/CD for ALONE

## What you will get
- Docker in Docker
- Jenkins with the blueocean plugin
- Docker local registry
- Docker local registry UI

## Prerequisites
- Git (tested in 1.8.3.1)
- Docker (tested in 20.10.10)
- Docker-compose (tested in 1.29.2)

## Installation
```bash
$ git clone https://github.com/inminhouse/alone-ci-cd.git
$ cd alone-ci-cd
$ sudo docker-compose up -d --build
```

## Jenkins
- Installation
    1. Go to your-server-address:8080 in your browser
    2. Unlock the jenkins
        ```bash
        $ sudo docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword 
        ```
    3. Install suggested plugins
    4. Create an admin account
    5. Define the host of jenkins
- Locale Configuration
    1. Go to Manage Jenkins > Manage Plugins > Available Tab
    2. Search 'Locale'
    3. Select Locale plugin in the list and click [install without restart]
    4. Go to Manage Jenkins > Configure System > Locale section
    5. Input 'en_US' in the field of [Default Language]
    6. Check the box of [Ignore browser preference and force this language to all users]
       <img src="./img/locale-config.PNG" width="100%" height="100%" />
    8. Save
- Maven Configuration
    1. Go to Manage Jenkins > Global Tool Configuration > Maven sesion
    2. Click [Add Maven]
    3. Fill the field of Name
    4. Select the version of maven you want to use
       <img src="./img/mvn-config.PNG" width="100%" height="100%" />
    5. Save
    6. Go to Dashboard > your project (which you want to build) > Configure (in the left menu) > Build tab
    7. Click [Add build step]
    8. Select [Invoke top-level Maven targets]
    9. Choose the maven 
    10. Fill out the goal
       <img src="./img/project-config-maven.PNG" width="100%" height="100%" />
- Docker Configuration
    1. Go to Manage Jenkins > Manage Plugins > Available Tab
    2. Search 'Docker'
    3. Select Docker and CloudBees Docker Build and Publish plugins in the list and click [install without restart]
    4. Go to Dashboard > your project (which you want to build) > Configure (in the left menu) > Build tab
    5. Click [Add build step]
    6. Select [Docker Build and Publish]
    7. Fill out the required fields
       <img src="./img/project-config-docker.PNG" width="100%" height="100%" />
    8. Save
    
## References
- https://www.jenkins.io/doc/book/installing/docker/
- https://docs.docker.com/registry/deploying/
- https://pkuwwt.github.io/techniques/2020-04-04-setup-a-private-docker-registry/
