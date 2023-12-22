
1. make folder: clair_local_poc/docker-compose.yml

2. make folder with: clair_local_poc/docker-utils/clair-config/config.yml

3. $docker-compose up -d
4. $docker-compose ps
5. $docker-compose exec clairctl  clairctl analyze -l <attack-coker-file-image>

eg: $docker-compose exec clairctl  clairctl analyze -l infoslack/dvwa

docker-compose exec clairctl clairctl analyze -l vulnerables/web-dvwa.


For scan a target:
1. pull the target container: 
$docker pull infoslack/dvwa
2. After completing the pulling, scan with:
$docker-compose exec clairctl clairctl analyze -l infoslack/dvwa
)https://peoplesblog.co.in/articles/locally-setup-and-scan-your-docker-images-via-clair.html
https://dev.to/softwaresennin/docker-security-clair-hno
https://www.techtarget.com/searchitoperations/tutorial/How-to-scan-Docker-images-for-vulnerabilities-with-Clair
https://medium.com/paloit/coreos-clair-part-2-installation-integration-558ec664cece


main aswome container security learning:
https://github.com/myugan/awesome-docker-security

1. make folder: clair_local_poc/docker-compose.yml

2. make folder with: clair_local_poc/docker-utils/clair-config/config.yml

3. $docker-compose up -d
4. $docker-compose ps
5. $docker-compose exec clairctl  clairctl analyze -l <attack-coker-file-image>

eg: $docker-compose exec clairctl  clairctl analyze -l infoslack/dvwa

docker-compose exec clairctl clairctl analyze -l vulnerables/web-dvwa.


For scan a target:
1. pull the target container: 
$docker pull infoslack/dvwa
2. After completing the pulling, scan with:
$docker-compose exec clairctl clairctl analyze -l infoslack/dvwa


### References:
1. https://peoplesblog.co.in/articles/locally-setup-and-scan-your-docker-images-via-clair.html
2. https://dev.to/softwaresennin/docker-security-clair-hno
3. https://www.techtarget.com/searchitoperations/tutorial/How-to-scan-Docker-images-for-vulnerabilities-with-Clair
4. https://medium.com/paloit/coreos-clair-part-2-installation-integration-558ec664cece
