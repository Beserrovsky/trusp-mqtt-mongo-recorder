mqtt-mongo-recorder
===========

This NodeJS application listens to MQTT messages and records them to MongoDB

Env
=======
node-js: v12.22.9
mongodb: v5.0.13

Mongo DB install on Ubuntu 22.04 LTS:
https://www.mongodb.com/community/forums/t/installing-mongodb-over-ubuntu-22-04/159931/82
https://wiki.crowncloud.net/?How_to_Install_Latest_MongoDB_on_Ubuntu_22_04

Example
=======

Clone the repository
```bash
$ git clone https://github.com/dennisdegreef/mqtt-mongo-recorder.git
$ cd mqtt-mongo-recorder
$ npm install
```

Start up the server by editing the config.js first to suit your needs
```bash
$ $EDITOR config.js
$ node server.js
```

Or by using environment variables
```bash
$ MQTT_HOSTNAME="192.168.0.1" node server.js
```

Publish some MQTT messages to try it out (I use mosquitto server for this, but whatever MQTT server should work)
```bash
$ mosquitto_pub -m "bar" -t "foo"
```

Let's see what's in here
```bash
$ mongo
> use mqtt
> db.message.find();
```


