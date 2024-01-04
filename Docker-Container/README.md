### Docker commands:
```
## For run:
$ docker run infoslack/dvwa
## For check, run or not:
$ docker ps
## For stop:
$ docker stop <conatiner-id>
## For docker image delete:
$ docker rmi <conatiner-id>
(-f for force to delete)
```
### Pull a Docker image:
```
$ docker pull infoslack/dvwa
```
### Docker network list:
```
$ docker network ls
```
### Docker-compose commands:
```
## For run:
$ docker-compose up
## For check, run or not:
$ docker-compose ps
## For stop:
$ docker-compose down
## Remove or Delete docker-compose image:
$ docker-compose down --rmi all --volumes
```

##### For Learning:
Awesome container security learning:
1. https://github.com/myugan/awesome-docker-security
