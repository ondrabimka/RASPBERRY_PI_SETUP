### Docker Installation

Quite ok to install docker on Raspberry Pi 4. I followed the official documentation (https://docs.docker.com/engine/install/ubuntu/) and it worked (almost) fine. Here are the steps:

1. Set up Docker's apt repository.
```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

2. Install the Docker packages.
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

3.  Verify that Docker is installed correctly by running the hello-world image.
```bash
sudo docker run hello-world
```
Voila! Docker is installed on your Raspberry Pi 4.

### Docker Compose Installation
Also docker compose is quite handy to manage multiple containers. Here are the steps to install docker compose on Raspberry Pi 4:

```bash
sudo apt  install docker-compose
```