# README

## Windows

Jenkins Docker running on Windows(WSL2).

Reference,

<https://www.jenkins.io/doc/book/installing/docker/>

### Build the Image

```bat
docker build -t jenkinsmaster .
```

### Create the Container and Run

```bat
docker run --name jenkinsmaster --restart=on-failure --detach ^
  --network jenkins --env DOCKER_HOST=tcp://docker:2376 ^
  --env DOCKER_CERT_PATH=/certs/client --env DOCKER_TLS_VERIFY=0 ^
  --volume jenkins-data:/var/jenkins_home ^
  --volume jenkins-docker-certs:/certs/client:ro ^
  --publish 8080:8080 --publish 50000:50000 jenkinsmaster
```

### macOS

Just pull the latest,

```bash
docker pull jenkins/jenkins:lts
# or
docker pull jenkins/jenkins:lts-jdk17
```
