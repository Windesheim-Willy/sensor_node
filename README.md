# Sensor node

## Installation on a Raspberry PI

### Install Ubiquity
https://downloads.ubiquityrobotics.com/pi.html

### disable WiFi

1. Start
* Select Preference
* Navigate to Network Connections
* Remove all WiFi connections

### Disable demo stuff

1. Enter `sudo systemctl disable magni-base` in a terminal window

### Enable SSH

1. Enter `sudo raspi-config` in a terminal window
* Select Interfacing Options
* Navigate to and select SSH
* Choose Yes
* Select Ok
* Choose Finish

### Change language and Time Settings

1. Enter `sudo raspi-config` in a terminal window
* Select Localisation Options
* Navigate to and select 'Change Locale'
* Select en_US.UTF8 UTF8 Enter
* Select Ok
* Choose Finish

### Change Timezone

1. Enter `sudo raspi-config` in a terminal window
* Select Localisation Options
* Navigate to and select 'Change Timezone'
* Navigate to and select 'Europe'
* Navigate to and select 'Amsterdam'
* Select en_US.UTF8 UTF8 Enter
* Choose Finish

### Install Software

Add in /bashsh
export ROS_MASTER_URI=http://192.168.0.10:11311/
