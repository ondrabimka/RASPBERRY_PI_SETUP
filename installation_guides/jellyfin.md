### Jellyfin (docker)

I will be installing Jellyfin using docker compose. 
BAsically just need to follow the steps in this link (docker compose part): https://jellyfin.org/docs/general/installation/container/

bash
```bash
mkdir jellyfin
cd jellyfin
```

Create a file called `docker-compose.yml` and paste the following content:

```bash
services:
  jellyfin:
    image: jellyfin/jellyfin
    container_name: jellyfin
    user: uid:gid
    network_mode: 'host'
    volumes:
      - /path/to/config:/config
      - /path/to/cache:/cache
      - type: bind
        source: /path/to/media
        target: /media
      - type: bind
        source: /path/to/media2
        target: /media2
        read_only: true
      # Optional - extra fonts to be used during transcoding with subtitle burn-in
      - type: bind
        source: /path/to/fonts
        target: /usr/local/share/fonts/custom
        read_only: true
    restart: 'unless-stopped'
    # Optional - alternative address used for autodiscovery
    environment:
      - JELLYFIN_PublishedServerUrl=http://example.com
    # Optional - may be necessary for docker healthcheck to pass if running in host network mode
    extra_hosts:
      - 'host.docker.internal:host-gateway'
```

Now run the following command to start the container:

```bash
docker-compose up -d
```

Jellyfin should be up and running on your Raspberry Pi 4. You can access it using your browser at http://IP_ADDRESS:8096.
