# push-data-demo
Jenkins -> push data to Pushgateway
Prometheus -> Collect Data
Grafana -> visualize Data

# How to run

## Requirements

docker
docker-compose

## Clone Source Code 

Get 'docker-compose.yml' and 'prometheus.yml' in the same directory

## Launch 

```
docker-compose up -d
```

## Configuration

### jenkins
url: http://localhost:8080/

username: admin

password is from the file "/var/jenkins_home/secrets/initialAdminPassword" in docker container

### Prometheus
http://localhost:9090

### Pushgateway
http://localhost:9091

### Grafana
url: http://localhost:3000

username: admin

password: admin

(Ask you to change password for when you first login)

## How to push a new metric

```Shell
echo "my_metric 42" | curl --data-binary @- http://localhost:9091/metrics/job/my_job
```





