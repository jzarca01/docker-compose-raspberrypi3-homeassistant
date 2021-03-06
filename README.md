This repository represents a home-assistant setup for the Raspberry pi 3 running Docker.

Currently this provides you with a Home Assistant server on http://raspberrypi.local:8123 and
an MQTT server (mosquitto) on port 1883.

### Installation

```
$ sudo apt-get install docker docker-compose
$ git clone https://github.com/jzarca01/docker-compose-raspberrypi3-homeassistant.git $HOME/homeassistant
```

Furthermore you will need to generate a mosquitto password file:

```
$ mkdir $HOME/mosquitto
$ mkdir $HOME/mosquitto/config
$ touch $HOME/mosquitto/config/users.passwd
$ docker-compose run --rm --no-deps -v "$(pwd)/mosquitto/config/users.passwd:/passwd" mosquitto mosquitto_passwd -b /passwd username password
```

## Running Home Assistant

```
$ cd $HOME/homeassistant
$ docker-compose build && docker-compose pull && docker-compose up -d
```
