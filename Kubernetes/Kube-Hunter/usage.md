## Installation:

### Using pip to install:
```
$ pip install kube-hunter
```
### Install from source repo:
```
$ git clone https://github.com/aquasecurity/kube-hunter.git
$ cd kube-hunte
$ pip install -r requirements.txt
```

### Usage:
```
$ kube-hunter list
## Scan a single remote host
$ kube-hunter    (press enter)
choose 1, then enter the remote IP address, eg. 172.12.0.1

## For check ip address:
$ kubectl get nodes -o wide
## Scan a multiple remote hosts
$ kube-hunter (press enter)
choose 1, then enter the remote IP addresses with comma, eg. 172.12.0.1,172.12.0.2

## For directly scan with args
$ kube-hunter --remote 172.12.0.1,172.12.0.2
## For output:
$ kube-hunter --remote 172.12.0.1 -report json

## For scanning by a pods
$ 
```

### After getting the vulnerabilities, for making report:
1. https://github.com/aquasecurity/kube-hunter/tree/main/docs/_kb

