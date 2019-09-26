Docker Installation
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
ls
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
