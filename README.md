# Webhook2MQTT
This is a fork of https://github.com/JoeRu/Webhook2MQTT which has been modified to better suite my use case.

Many of the scripts and setup have been borrowed from https://github.com/tiangolo/meinheld-gunicorn-flask-docker

## Setup
change in docker-compose the environment variable to connect to your mqtt server
```docker-compose
MQTT_HOST '192.168.176.6'
MQTT_PORT: 1883
MQTT_PATH: 'webhook'
MQTT_USER: 'myuser' #Optional
MQTT_PASS: 'mypass' #Optional
```

iIt is strongly suggested to put some reverse-proxy ahead of your installation. 

## Architecture

Pretty simple - a flask app initiating a new thread to forward the expected json object to mqtt.
