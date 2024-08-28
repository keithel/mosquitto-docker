# eclipse-mosquitto docker config and storage

This is a directory storing the configuration and data for an eclipse-mosquitto mqtt
server. In here you will find information on what the different files and
folders are, as well as how to fetch the docker image and launch the container.

# File info

 * `mosquitto.conf` - this is the configuration file for the MQTT server.
 * `data` - This is the directory where the persistent data - messages received,
etc are stored. This is long-lived, living beyond just the life of the docker
container.
 * `log` - A directory holding mosquitto's runtime logs.

# Fetching the image:

```
docker pull eclipse-mosquitto
```

# Running the container:

```
docker run -it -p 1883:1883 -p 9001:9001 -v ./mosquitto.conf:/mosquitto/config/mosquitto.conf -v ./data:/mosquitto/data -v ./log:/mosquitto/log eclipse-mosquitto
```

# Licence

Eclipse Mosquitto is released under the EPL/EDL. For more information, see
https://hub.docker.com/_/eclipse-mosquitto
