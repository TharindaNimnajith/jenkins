docker --version

docker images

docker pull jenkins/jenkins:lts

docker run --detach --publish 8080:8080 --volume
jenkins_home:/var/jenkins_home --name jenkins jenkins/jenkins:lts

docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
