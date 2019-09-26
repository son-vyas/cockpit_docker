### Docker Installation
```
$ sudo dnf install docker
```
Start the docker daemon 
```
$ sudo systemctl start docker
```
Test docker installation
```
$ docker run hello-world
```
List all images docker images 
```
$ ls
```

### Docker Compose

```
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

Apply executable permissions to the binary
```
$ sudo chmod +x /usr/local/bin/docker-compose
```

Create Symbolic link to the binary
```
$ sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

Verify installation
```
$ docker-compose --version
```
### Add user to docker group

```
$ groupadd docker
```
Add docker group to supplementary group of user
```
$ usermod $USER -aG docker
```
Activate group changes
```
$ newgrp docker
```
### Cockpit installation

```
$ docker volume create telegraf-volume
```
Navigate to ci-scripts/infra-setup/roles/rrcockpit/files
```
$ cd ci-scripts/infra-setup/roles/rrcockpit/files
./development_script.sh -s
```
It is time consuming at first run. So relax, it will continuosly pull containers.

create-api-key.py

```
$ cd files/grafana/
$ ./create-api-key.py --key-name foo > grafana.key
```
export-grafana.py and import-grafana.py
```
./export-grafana.py --host http://172.18.0.6:3000
./import-grafana.py --host http://172.18.0.6:3000

```
