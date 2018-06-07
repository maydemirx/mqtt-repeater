# mqtt-repeater 


[![npm version](https://badge.fury.io/js/mqtt-repeater.svg)](https://badge.fury.io/js/mqtt-repeater)
[![Build Status](https://travis-ci.com/maydemirx/mqtt-repeater.svg?branch=master)](https://travis-ci.com/maydemirx/mqtt-repeater) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/bf809192995b4fc782995c4e5a7d2e26)](https://www.codacy.com/app/maydemirx/mqtt-repeater?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=maydemirx/mqtt-repeater&amp;utm_campaign=Badge_Grade) 

This NodeJS application publishes messages from a mqtt broker to another mqtt broker. You can set the topic that you want to exchange by environment variables.

Example
=======

Clone the repository
```bash
$ git clone https://github.com/inhedron/mqtt-repeater.git
$ cd mqtt-repeater
$ npm install
```

You can set options by environment variables
```bash
$ TARGET_MQTT_HOST="mqtt://192.168.0.2" SOURCE_MQTT_HOST="mqtt://192.168.0.1" node index.js
```

If you run the application with this config the application read all messages from the broker that installed on 192.168.0.1 and publish them to the broker that installed on 192.168.0.2. For details please check the config.js file at the source tree or check the options stage.

### Options

Option                 | Type          | Default              | Description
-----------------------|---------------|----------------------|----------------------------
SOURCE_MQTT_HOST | String | mqtt://broker | Hostname or ip address of the source broker that you want to read messages 
SOURCE_MQTT_CONF | JSON   | {"clean": false, "port": 1885, "clientId": "mqtt-repeater-source-client"} | The configuration of the source broker
TARGET_MQTT_HOST | String | mqtt://broker | Hostname or ip address of the source broker that you want to publish messages 
SOURCE_MQTT_CONF | JSON   | {"clean": false, "port": 1883, "clientId": "mqtt-repeater-target-client"} | The configuration of the target broker
SUBSCRIPTIONS    | Array  | ["#"] | The subscribe list of the messages. The application subscribe all of them, read messages from these topics and publish them to target broker
