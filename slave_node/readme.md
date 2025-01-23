```bash
docker run -d \
--name jenkins-slave \
-v /var/run/docker.sock:/var/run/docker.sock \
-e JENKINS_URL=http://192.168.1.120:8070/ \
-e JENKINS_AGENT_NAME=slave-node1 \
-e JENKINS_SECRET=<agent-secret> \
-e JENKINS_WORKDIR=/home/jenkins \
jenkins/agent
```