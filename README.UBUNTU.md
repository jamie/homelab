## System setup

### SSH

`sudo apt install openssh-server`

### Docker

`sudo apt install docker docker-compose`

### Portainer

```
docker volume create portainer_data
docker run -d \
  -p 9443:9443 \
  --name portainer \
  --restart=always \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v portainer_data:/data portainer/portainer-ee:latest`
```

### Adblock

Running Adguard Home or PiHole, need to disable default DNS cache.

```
### systemd-resolvd, port 53
sudo systemctl disable systemd-resolved.service
sudo systemctl stop systemd-resolved

# Edit /etc/NetworkManager/NetworkManager.conf
# section [main]
# dns=default

rm /etc/resolv.conf
sudo systemctl restart NetworkManager
```
