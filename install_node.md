### Install Raspbian with Desktop
<https://www.raspberrypi.org/downloads/raspbian/>

### Enable SSH

1. Enter `sudo raspi-config` in a terminal window
* Select Interfacing Options
* Navigate to and select SSH
* Choose Yes
* Select Ok
* Choose Finish

### Enable VNC

1. Enter `sudo raspi-config` in a terminal window
* Select Interfacing Options
* Navigate to and select VNC
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

```
cd /opt
sudo git clone https://github.com/xxxx/xxxx.git willy
cd willy
sudo git checkout feature/infrastructure # TODO remove
sudo ./INSTALL

```