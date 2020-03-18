## install
```
docker run -p 9090:8080 -p 50000:50000 -v </local/drive>:/var/jenkins_home --name jenkins jenkins/jenkins:lts-alpine
```

## admin pass
```
docker exec jenkins bash -c 'cat $JENKINS_HOME/secrets/initialAdminPassword'
```

## SSL error for git plugin
```
docker exec -it jenkins git config --global http.sslVerify false
```

