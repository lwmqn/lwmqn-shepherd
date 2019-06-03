<img src="https://raw.githubusercontent.com/lwmqn/documents/master/media/mqtt.png" align="right" height="96" width="96" />

# mqtt-shepherd
Network server and manager for the lightweight MQTT machine network (LWMQN)

[![NPM](https://nodei.co/npm/mqtt-shepherd.png?downloads=true)](https://nodei.co/npm/mqtt-shepherd/)

[![Travis branch](https://img.shields.io/travis/lwmqn/mqtt-shepherd/master.svg?maxAge=2592000)](https://travis-ci.org/lwmqn/mqtt-shepherd)
[![Coverage Status](https://coveralls.io/repos/github/lwmqn/mqtt-shepherd/badge.svg?branch=master)](https://coveralls.io/github/lwmqn/mqtt-shepherd?branch=master)
[![npm](https://img.shields.io/npm/l/mqtt-shepherd.svg?maxAge=2592000)](https://www.npmjs.com/package/mqtt-shepherd)
[![Gitter](https://img.shields.io/gitter/room/lwmqn/Lobby.svg)](https://gitter.im/lwmqn/Lobby) [![Greenkeeper badge](https://badges.greenkeeper.io/lwmqn/mqtt-shepherd.svg)](https://greenkeeper.io/)

Make sure you are with version >= 0.7.0, the old bumps before 0.7.0 are all deprecated.

-------

## Documentation

Please visit the [Wiki](https://github.com/lwmqn/mqtt-shepherd/wiki).

-------

## Overview

Lightweight MQTT machine network ([**LWMQN**](http://lwmqn.github.io)) is an open source project that follows part of [**OMA LWM2M v1.0**](http://technical.openmobilealliance.org/Technical/technical-information/release-program/current-releases/oma-lightweightm2m-v1-0) specification to meet the minimum requirements of machine network management.

* Server-side library: **mqtt-shepherd** (this module)
* Client-side library: [**mqtt-node**](https://github.com/lwmqn/mqtt-node)
* [**A simple demo webapp**](https://github.com/lwmqn/lwmqn-demo)

![LWMQN Network](https://raw.githubusercontent.com/lwmqn/documents/master/media/lwmqn_net.png)

-------

## Installation

> $ npm install mqtt-shepherd --save


## Basic Usage

```js
var MqttShepherd = require('mqtt-shepherd');
var qserver = new MqttShepherd();   // create a LWMQN server

qserver.on('ready', function () {
    console.log('Server is ready.');

    // when server is ready, allow devices to join the network within 180 secs
    qserver.permitJoin(180);
});

qserver.start(function (err) {      // start the sever
    if (err)
        console.log(err);
});

// That's all to start a LWMQN server.
// Now qserver is going to automatically tackle most of the network managing things.
```

-------

## License

Licensed under [MIT](https://github.com/lwmqn/mqtt-shepherd/blob/master/LICENSE).

