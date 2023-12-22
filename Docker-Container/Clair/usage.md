### Installation for Clair:

#### Make folder
1. make folder: clair_local_poc/docker-compose.yml
```
version: '2.1'

services:
  postgres:
    image: postgres:9.6
    restart: unless-stopped
    volumes:
      - ./docker-utils/postgres-data/:/var/lib/postgresql/data:rw
    environment:
      - POSTGRES_PASSWORD=ChangeMe
      - POSTGRES_USER=clair
      - POSTGRES_DB=clair

  clair:
    image: quay.io/coreos/clair:v4.3.6
    restart: unless-stopped
    volumes:
      - ./docker-utils/clair-config/:/config/:ro
      - ./docker-utils/clair-tmp/:/tmp/:rw
    depends_on:
      postgres:
        condition: service_started
    command: [--log-level=debug, --config, /config/config.yml]
    user: root

  clairctl:
    image: jgsqware/clairctl:latest
    restart: unless-stopped
    environment:
      - DOCKER_API_VERSION=1.24
    volumes:
      - ./docker-utils/clairctl-reports/:/reports/:rw
      - /var/run/docker.sock:/var/run/docker.sock:ro
    depends_on:
      clair:
        condition: service_started
    user: root
```
2. make folder with: clair_local_poc/docker-utils/clair-config/config.yml
```
clair:
  database:
    type: pgsql
    options:
      source: postgresql://clair:ChangeMe@postgres:5432/clair?sslmode=disable
      cachesize: 16384
  api:
    port: 6060
    healthport: 6061
    timeout: 900s
  updater:
    interval: 2h
  notifier:
    attempts: 3
    renotifyinterval: 2h
```

3. Pull for install clair:
```
$ docker-compose up -d
```
4. For check, run or not:
```
$ docker-compose ps
```
#### For tetsing commands:
```
$ docker-compose exec clairctl clairctl analyze -l <attack-coker-file-image>

eg: $ docker-compose exec clairctl clairctl analyze -l infoslack/dvwa
```

### References:
1. https://peoplesblog.co.in/articles/locally-setup-and-scan-your-docker-images-via-clair.html
2. https://dev.to/softwaresennin/docker-security-clair-hno
3. https://www.techtarget.com/searchitoperations/tutorial/How-to-scan-Docker-images-for-vulnerabilities-with-Clair
4. https://medium.com/paloit/coreos-clair-part-2-installation-integration-558ec664cece
