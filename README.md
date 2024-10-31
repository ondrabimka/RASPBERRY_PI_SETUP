### Welcome to RASPBERRY_PI_SETUP page!

In this repo I am collecting all the information that I have gathered while setting up my Raspberry Pi 4. I am using it as ubuntu server and I have installed the following services on it:
- [x] Docker [Installation Guide](installation_guides/Install_docker.md)

### Pre-requisites
- [x] Raspberry Pi 4
- [x] Micro SD card
- [x] Power supply

### Steps
1. Follow: [Download Ubuntu Server](https://ubuntu.com/tutorials/how-to-install-ubuntu-on-your-raspberry-pi#1-overview)

2. Then ssh into your Raspberry Pi using the following command:
```bash
ssh <username>@<Raspberry Pi’s IP address>
```
or 
```bash
ssh <username>@<hostname>
```

Note: If you get following error:
'''
WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED! 
'''
Then run the following command:
```bash
ssh-keygen -R <hostname>
```