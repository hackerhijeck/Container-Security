## Installation for Lynis:

#### Using yum to install:
```
$ yum install lynis
```
#### Direct install with Debian:
```
$ apt-get install lynis
```
#### Installation via Git
```
$ cd /usr/local
$ git clone https://github.com/CISOfy/lynis.git
$ cd lynis

## For run first
$ lynis audit system
```
#### Using Brew for install:
```
$ brew install lynis
```
##### Installation via direct download:
```
$ mkdir -p /usr/local/lynis
$ cd /usr/local
$ wget https://downloads.cisofy.com/lynis/lynis-3.0.9.tar.gz

## For extract
$ tar xfvz lynis-<version>.tar.gz
```
### Usage:
```
$ lynis audit system --quick --auditor "The Auditor"
$ lynis audit dockerfile --quick --auditor "The Auditor"
```
#### References:
1. https://cisofy.com/documentation/lynis/get-started/
2. https://cisofy.com/documentation/lynis/
