# TibiaData docker-compose

TibiaData docker-compose configurations for TibiaData container, Kong API gateway and Konga admin GUI.

## Folders

There are following folders..

### [kong](./kong/)

Used to get [Kong API](https://github.com/Kong/docker-kong) gateway up and runnig.

The installation itself is empty and you'd need to create services and routes yourself (as it is right now). Or import from a backup, if you have any previous installation.

### [konga](./konga/)

Used to get [Konga](https://github.com/pantsel/konga) up and running.

This is for administration of the Kong API gateway.

### [tibiadata](./tibiadata/)

Used to get [TibiaData API](https://github.com/TibiaData/tibiadata-api-go) up and running.

## Usage

Here is a list of useful `docker compose` commands.

Pull service images:
```console
docker compose pull
```

Create and start containers:
```console
docker compose up -d
```

Stop and remove containers, networks:
```console
docker compose down
```

View output from containers:
```console
docker compose logs -n 25 -f
```

## Credits

- Authors: [Tobias Lindberg](https://github.com/tobiasehlert) – [List of contributors](https://github.com/TibiaData/tibiadata-docker-compose/graphs/contributors)
- Distributed under [MIT License](LICENSE)
