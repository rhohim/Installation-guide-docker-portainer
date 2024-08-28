1. Update Repository

```
sudo apt update
```

2. Install Package Yang diperlukan

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
```

3. Tambah GPG Key

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

4. Tambah Docker repository

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

5. Pastikan sumber

```
apt-cache policy docker-ce
```

6. Install Docker

```
sudo apt install docker-ce -y
```

7. Cek status Docker

```
sudo systemctl status docker
```

8. create the volume that Portainer Server will use to store its database

```
docker volume create portainer_data
```

9. download and install the Portainer Server container

```
docker run -d -p 8000:8000 -p 9000:9000 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ee:2.21.0
```

10. check to see whether the Portainer Server container has started by running

```
docker ps -a
```

11. Logging In Portainer

```
https://localhost:9000
```

Documentation Portainer https://docs.portainer.io/start/install/server/docker/linux

```

```
