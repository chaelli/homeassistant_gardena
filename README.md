[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg?style=for-the-badge)](https://github.com/custom-components/hacs)

# Home assistant Gardena Smart support

This is a custom component to support Gardena smart devices. All devices will be automatically discovered.
It uses a seperate library (written by github user @wijnandtop), that has additional details in it's documentation. You can find it here: https://github.com/wijnandtop/wt.pygardena

Currently it supports the following devices:

## Sileno Smart Mower
Mowers will be added as vacuum cleaners.
The vacuum cleaner is the closest thing to a lawn mower, it has characteristics like a base station, being a robot, supports simular command (stop, start, dock) and has a battery status.
Start will trigger 24h of mowing.

## Smart Sensor 
https://www.gardena.com/int/products/smart/smart-system/gardena-smart-sensor/967044801/
This device is registered as multiple sensors:

* Soil temperature (sensor as class temperature)
* Soil humidity (sensor as class humidity)
* Light (sensor as class illuminance)
* Ambient temperature (sensor as class temperature)
* Frost warning (binary_sensor as class cold)

## Watering Computer
Supports:
Start (triggers 30min of watering)
Stop 

!Concern, It could be possible that the irrigation control offered by Gardena will break this plugin, since this implementation only assumes one outlet! https://www.gardena.com/int/products/watering/water-controls/pim94995109/967669901/

## Usage
1. Register this repository in the Community Store under "Settings" tab. Then follow the instructions to install the integration.

2. Add these lines in your configuration.yaml. Ensure that you have your Gardena credentials properly configured in Homeassistant, like in the secrets.yaml file.

```
gardena:
  username : !secret gardena_user
  password : !secret gardena_password
```

3. Restart Homeassistant

## Tested with:
 * Mower: Sileno smart (the one with a working capacity of 1000m2)
 * Smart Sensor