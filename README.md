# jenkins_cluster

This is an example/workable POC to get jenkins up and running with agents using a shared docker socket.

```
DOCKER_OPTS="-H unix:///var/run/docker.sock -H tcp://0.0.0.0:2375"
```
Must be in /etc/init/docker.conf

To run

``` 
docker-compose up
```

In Jenkins set the docker connection to `tcp://HOSTNAME:2375` and use jenkins credentials for the `jenkinscluster_jenkins_slave` image to jenkins/jenkins
