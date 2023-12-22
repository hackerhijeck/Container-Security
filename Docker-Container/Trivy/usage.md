## Installation for Trivy:

#### Using brew to install (Linux):
```
$ brew install trivy
```
#### Using Deb file to install (Ubuntu/Debian):
```
$ wget https://github.com/aquasecurity/trivy/releases/download/v0.48.1/trivy_0.48.1_Linux-64bit.deb
$ sudo dpkg -i trivy_0.48.1_Linux-64bit.deb
```

#### Using github repo to install:
```
1. Download the file for your operating system/architecture from GitHub Release assets
$ curl -LO https://url.to/trivy.tar.gz
2. Unpack
$ tar -xzf ./trivy.tar.gz
3. Put the binary somewhere in your $PATH 
$ mv ./trivy /usr/local/bin/
4. $ chmod +x ./trivy)
```
#### Using Bash script to install:
```
$ curl -sfL https://raw.githubusercontent.com/aquasecurity/trivy/main/contrib/install.sh | sh -s -- -b /usr/local/bin v0.48.1
```
#### Using github source to install:
```
$ git clone --depth 1 --branch v0.48.1 https://github.com/aquasecurity/trivy
$ cd trivy
$ go install ./cmd/trivy
```
### Usage for tetsing:
```
$ trivy image infoslack/dvwa
$ trivy image --severity HIGH,CRITICAL,MEDIUM,LOW infoslack/dvwa

### Use for IPwise
$ trivy image --server http://127.0.0.1:80 infoslack/dvwa

### Use for output
$ trivy image --format template @contrib/html.tpl -o scan.html infoslack/dvwa
$ trivy image --format json --output result.json infoslack/dvwa

- formats: table,json,template,sarif,cyclonedx,spdx,spdx-json,github,cosign-vuln
```
### This tools facilities:
 ``` 
  aws         [EXPERIMENTAL] Scan AWS account
  config      Scan config files for misconfigurations
  filesystem  Scan local filesystem
  image       Scan a container image
  kubernetes  [EXPERIMENTAL] Scan kubernetes cluster
  repository  Scan a repository
  rootfs      Scan rootfs
  sbom        Scan SBOM for vulnerabilities
  vm          [EXPERIMENTAL] Scan a virtual machine image
```
### References:
https://aquasecurity.github.io/trivy/v0.48/getting-started/installation/
https://www.howtogeek.com/devops/how-to-use-trivy-to-find-vulnerabilities-in-docker-containers/
