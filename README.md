# Homebridge Pi Garage Door Opener With Sensor


This is a [homebridge](https://github.com/nfarina/homebridge) plugin to make a Raspberry Pi connected with a Relay Board into a Garage Door Opener, via the Home app on iOS using Homekit.  It uses a magnetic switch to determine the state of the garage door, open or closed. The wires from the Relay go into the same ports as the wired button for the garage door. When the Relay closes the circuit it acts like the button was pushed. Tested with iOS 13.


### Start on boot

Have the "homebridge" command run at boot.


### Sample Config

Rename config.sample.json to config.json and place in .homebridge/config.json

```json
{
  "bridge": {
      "name": "Garage Homebridge",
      "username": "CC:22:3D:E3:CE:30",
      "port": 51826,
      "pin":"031-45-154",
      "manufacturer": "@nfarina",
      "model": "Homebridge",
      "serialNumber": "0.4.20"
  },
  "description": "The garage home bridge",
  "accessories": [{
    "accessory": "Garage Door Opener",
    "name": "Garage Door",
    "doorRelayPin": 11,
    "doorSensorPin": 16,
    "invertDoorState": false,
    "invertSensorState": false,
    "duration_ms": 500
  }]
}
```

### How to Setup

```
sudo npm install -g --unsafe-perm homebridge
sudo npm install -g --unsafe-perm homebridge-garage-door-wsensor
```
Rename config.sample.json to config.json and place in .homebridge/config.json


### How to Start
Run the following command
```
homebridge
```