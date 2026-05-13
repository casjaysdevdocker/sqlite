## 👋 Welcome to sqlite 🚀  

sqlite README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update sqlite
```
  
## Install and run container
  
```shell
dockerHome="/var/lib/srv/$USER/docker/casjaysdevdocker/sqlite/sqlite/latest/rootfs"
mkdir -p "/var/lib/srv/$USER/docker/sqlite/rootfs"
git clone "https://github.com/dockermgr/sqlite" "$HOME/.local/share/CasjaysDev/dockermgr/sqlite"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/sqlite/rootfs/." "$dockerHome/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-sqlite-latest \
--hostname sqlite \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$dockerHome/data:/data:z" \
-v "$dockerHome/config:/config:z" \
-p 80:80 \
casjaysdevdocker/sqlite:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/sqlite
    container_name: casjaysdevdocker-sqlite
    environment:
      - TZ=America/New_York
      - HOSTNAME=sqlite
    volumes:
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/sqlite/sqlite/latest/rootfs/data:/data:z"
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/sqlite/sqlite/latest/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/sqlite
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/sqlite" "$HOME/Projects/github/casjaysdevdocker/sqlite"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/sqlite"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
