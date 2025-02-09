### Filebrowser (Docker)

Filebrowser is a lightweight file manager that runs in the browser. It is a great tool to manage files on your server.

I will be installing Filebrowser using docker compose.

1. Create a directory for filebrowser and navigate to it:
```bash
mkdir filebrowser
cd filebrowser
```

2. Create a file called `docker-compose.yml` and paste the following content:
```bash
services:
  filebrowser:
    image: filebrowser/filebrowser
    container_name: filebrowser
    ports:
      - "8080:80"
    volumes:
      - /path/to/config:/config
      - /path/to/data:/srv
    restart: 'unless-stopped'
```

3. Now run the following command to start the container:
```bash
docker-compose up -d
```

Filebrowser should be up and running on your Raspberry Pi 4. You can access it using your browser at http://IP_ADDRESS:8080.

Default username: `admin`
Default password: `admin`