# Set up docker
- $`sudo su`
- $`apt install docker.io`
- $`systemctl start docker`
- $`systemctl enable docker`

# Run the container
- Make sure to map to correct ports for you
- $`docker run --restart always -d -p 8081:8080 -p 50001:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts`

# Setup
- Go to the address of the server followed by the port you exposed externally e.g. 8081
- Create a user account
- Can find the credentials by doing
- $`docker exec -it <CONTAINER_NAME> /bin/bash`

# finding the admin key
- $`cat var/jenkins_home/secrets/initialAdminPassword`
- $`exit`

# Set up Jenkins
- New item
- Freestyle project
- Give it a name
- Ok
- General
    - `GitHub project`
    - `<PROJECT_URL>`
- Source Code Management
    - `<REPOSITORY__URL>`
    - `<BRANCH_TO_BUILD>`
- Build Triggers
    - `GitHub hook trigger for GITScm polling`


# Set up Git webhook
- Enter address of your server
- `<SERVER_URL>/github-webhook/`
- Set content type to `application/json`
- `Just push events`
- Save