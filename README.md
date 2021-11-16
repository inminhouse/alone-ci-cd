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
    1. go to your-server-address:8080 in your browser
    2. unlock the jenkins
        ```bash
        $ sudo docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword 
        ```
    3. install suggested plugins
    4. create an admin account
    5. define the host of jenkins
- Locale Configuration
    1. go to Manage Jenkins > Manage Plugins > Available Tab
    2. Search 'Locale'
    3. Select Locale plugin in the list and click [install without restart]
    4. go to Manage Jenkins > Configure System > Locale section
    5. Input 'en_US' in the field of [Default Language]
    6. Check the box of [Ignore browser preference and force this language to all users]
    7. Save

## References
- https://www.jenkins.io/doc/book/installing/docker/
- https://docs.docker.com/registry/deploying/
- https://pkuwwt.github.io/techniques/2020-04-04-setup-a-private-docker-registry/
