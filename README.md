# Installation

```
cp .env.example .env
# fill .env with your values (explanation below)
docker-compose up -d
docker-compose exec wireguard /app/show-peer PEER_NAME
```

## `.env` file explanation

```
PUID=0 # PUID and PGID - id/group of `./config` contents owner. useful for backups
PGID=0 # use `id` command to know your current id/group
TZ=Europe/Moscow

# optional variables:
SERVERURL=DOMAIN_OR_IP_HERE
SERVERPORT=51820 # also used in docker-compose.yml `ports:` binding
PEERS=mikrotikHome,onePlus # peers (clients) names, separated by comma. alphabet only. run `docker-compose up -d` after changing this line
PEERDNS=auto # which DNS servers should use clients. `auto` - use server's DNS resolver
INTERNAL_SUBNET=10.13.13.0 # subnet for clients
ALLOWEDIPS=0.0.0.0/0 # route all traffic through VPN
```

See more instructions/explanations here:
- https://github.com/linuxserver/docker-wireguard
- https://igancev.ru/2021-02-21-vpn-wireguard-docker (rus guide)
- https://markontech.com/linux/install-wireguard-vpn-server-with-docker/ (eng guide)

