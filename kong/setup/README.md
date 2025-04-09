# kong - initial setup

Below are some initial setup steps to consider.

> [!NOTE]  
> Following commands below are written for Debian 11 on a fresh installed system.

## docker

Docker has no settings by default regarding logrotation, so you need to add those so that your server doesn't get full.

In the `config/` folder you can find [docker-daemon.json](./config/docker-daemon.json), which contains the retention settings for docker.

### Steps

1. Copy config/docker-daemon.json to docker

   ```console
   sudo cp config/docker-daemon.json /etc/docker/daemon.json
   ```

1. Restart docker (containerd)
   ```console
   sudo systemctl restart containerd.service
   ```

## systemd

Due to the configuration of restart in [docker-compose.yml](docker-compose.yml), the Kong gateway is not starting on boot.

Therefor you need to add Kong to systemd so that it starts.

In the `config/` folder you can find [systemd-kong.service](./config/systemd-kong.service) which you should place in the appropriate location.

Adjust the location where the docker-compose.yml file is located on your system, else it will try to run docker compose in `/opt/tibiadata/tibiadata-docker-compose/kong`.

### Steps

1. Copy config/system-kong.service file to systemd

   ```console
   sudo cp config/system-kong.service /lib/systemd/system/kong.service
   ```

1. Edit the kong.service file

   ```console
   sudo vim /lib/systemd/system/kong.service
   ```

1. Enable systemd to start kong on boot

   ```console
   sudo systemctl enable kong.service
   ```
