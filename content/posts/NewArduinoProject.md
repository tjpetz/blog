+++
date = '2019-12-14T10:33:00-04:00'
draft = false
title = 'New Arduino Project'
+++

I’m working on tracking down and resolving a humidity problem in our home. While I have some basic measurements of humidity through our Nest Thermostat and a Canary device I want broader coverage so I can measure localized problem areas. The relatively new Arduino 33 BLE Sense looks to be a great device to meet my needs.

I’m creating a simple network combining BLE (Bluetooth Low Energy) and WiFi. I’m planning to use an Arduino 33 BLE Sense to measure the environment. the Arduino 33 BLE Sense doesn’t have Wifi. I’m planning to use an Arduino 33 IoT to act as a “gateway”, polling the Sense for measurements and periodically publishing them to an MQTT broker. The MQTT broker will be Mosquitto running on a Raspberry Pi.

I’m planning to use NodeRed to pull the message off MQTT, store them in an Influx db, and then graph the results in Grafina. I plan to do this all in Docker images on a Raspberry Pi.

This project will evolve over time. I will be publishing the code as it evolves over on Git Hub. I plan for this to be a bit of an example of how I incrementally develop systems, therefore I’ll be publishing rather raw and unpolished code in commits on GitHub.

If you’re interested follow along on GitHub at [https://github.com/tjpetz/NanoBLESensors](https://github.com/tjpetz/NanoBLESensors).
