# Aura monitoring with TenderDuty v2
https://github.com/blockpane/tenderduty
Tenderduty is a comprehensive monitoring tool for Tendermint chains. Its primary function is to alert a validator if they are missing blocks, and has many other features.

# Installation with Docker

`curl -fsSL https://get.docker.com | sh`

# Configure

```mkdir tenderduty && cd tenderduty```
```docker run --rm ghcr.io/blockpane/tenderduty:latest -example-config >config.yml```
edit *config.yml* and add chains, notification methods etc.
```docker run -d --name tenderduty -p "8888:8888" -p "28686:28686" --restart unless-stopped -v $(pwd)/config.yml:/var/lib/tenderduty/config.yml ghcr.io/blockpane/tenderduty:latest```
```docker logs -f --tail 20 tenderduty```

# Dashboard

Dashboard will be public at `http://YOUR_SERVER_IP:8888`

# Public RPCs

```
https://rpc.euphoria.aura.network:443
https://snapshot-1.euphoria.aura.network:443
https://snapshot-2.euphoria.aura.network:443
```