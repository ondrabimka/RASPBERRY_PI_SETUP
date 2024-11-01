### Home Assistant (docker)

You can use following tutorial to install it directly using imager: https://www.home-assistant.io/installation/raspberrypi, however I will be installing it using docker container.

All you have to do is to follow the steps in this link: https://www.home-assistant.io/installation/linux. 

If you already have docker up and running all you have to run is (fill in the parameters):
```bash
docker run -d \
  --name homeassistant \
  --privileged \
  --restart=unless-stopped \
  -e TZ=MY_TIME_ZONE \
  -v /PATH_TO_YOUR_CONFIG:/config \
  -v /run/dbus:/run/dbus:ro \
  --network=host \
  ghcr.io/home-assistant/home-assistant:stable
```

Now validate that the docker image is running:
```bash
docker ps
```

If yes, you should be able to access Home Assistant using your browser at http://IP_ADDRESS:8123.