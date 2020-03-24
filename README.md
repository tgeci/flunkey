# Flunkey Mirror
---
![image](https://user-images.githubusercontent.com/4592657/77485129-ac816900-6e2c-11ea-8dc0-144a6f164cfc.png)
Flunkey Mirror is a open source Python and Vue.js powered smart mirror project inspired by other smart mirror project like @evancohen's one.

# Why annother smart mirror project ?
---
Most of open source smart mirror projects are based on heavy frontend frameworks like Angular or as combination of a lot node modules. 
This project seperates frontend and backend and uses lightweight frameworks to be easy expandable.

# Architecture overview
---
Flunkey is based on four components **flunkey-glass**, **flunkey-api**, **flunkey-utils** and the **flunkey-app**.
![image](https://user-images.githubusercontent.com/4592657/77485502-945e1980-6e2d-11ea-8abd-fb6a1dfbe0ec.png)

## flunkey-glass
**flunkey-glass** is the component which is responsible for the presantation of information on mirror. 
![image](https://user-images.githubusercontent.com/4592657/77486610-7645e880-6e30-11ea-9d5f-d64ac04adf1d.png)
Technically it is a electron-vue app running in fullscreen of a Raspberry Pi 4. Every widget on it is a Vue.js Component, which loads data from the **flunkey-api**.

## flunkey-api
**flunkey-api** is the component with the main logic. Technically it's a Flask App with Blueprints and represents a api based middleware. 
The exposed endpoints will gather their information by connecting to remote API's like Spotify, Hue, FritzBox, OpenWeatherMap. It also interacts with the Mongo Database for configuration.

## flunkey-utils
**flunkey-utils** is a collection of Python scripts for Face Model Training and Recognition and other related scripts and systemd unit files. 

## flunkey-app
**flunkey-app** is a web interface to see and manage configuration objects.
![image](https://user-images.githubusercontent.com/4592657/77487388-a7bfb380-6e32-11ea-8787-57841a47349e.png)
