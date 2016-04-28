---
layout: page
title: Service Credentials
description: dev2
date: "2014-12-18 21:49"
sidebar: true
comments: false
sharing: true
footer: true
published: true
---

Default log-in credentials for latest [pre-built emonPi/emonBase ready-to-go SD card](https://github.com/openenergymonitor/emonpi/wiki/emonSD-pre-built-SD-card-Repository-&-Change-Log).

**Note: Before changing any password the root file-system will need to be put into Read Write mode with command `$rpi-rw`. When finished but file-sysem back to Read Only with `$rpi-ro`.**

# SSH

To connect to emonPi / emonBase via ssh:

 - Linux / Mac : open terminal window `$ ssh pit@emonpi` or `$ ssh pi@<IP ADDRESS>`
 - Windows: use [Putty application](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)
 - Google search `Raspberry Pi SSH` for many tutorials

**SSH: port 22 user,pass:`pi`,`emonpi2016`**

*On older emonSD images ssh password is `raspberry`, see emonSD [repository & changelog](https://github.com/openenergymonitor/emonpi/wiki/emonSD-pre-built-SD-card-Download-&-Change-Log)*

Once logged in change password with: `$ passwd`

## MYSQL

MYSQL: `root` user password is `emonpimysql2016` and mysql `emoncms` user password is `emonpiemoncmsmysql2016`


## Mosquitto MQTT

Mosquitto MQTT: port:1883 user,pass:`emonpi`,`emonpimqtt2016`

Generate a new password using `sudo mosquitto_passwd -c /etc/mosquitto/passwd <username>`. Then restart mosquitto `sudo service mosquitto restart`.

If Mosquitto MQTT authenticaion details are changed they will also need to changed in:

```bash
~/emonpi/lcd/emonPiLCD.py
~/data/emonhub.conf
/var/www/emoncms/settings.php
~/oem_openHab/openHab.cfg (symlined to /etc/openhab/configurations/openhab.cfg)
and node red using flows editor
```

**Caution changes to `emonPiLCD.py` and `settings.php` will be overwritten by emonPi update. Recommended to undertake manual *git pull(s)* to update instead.**

## NodeRED

NodeRED: port:1880 user,pass:`emonpi`,`emonpi2016`

change it here:  `~/data/node-red/settings.js`


## OpenHab

OpenHab port:8080 user,pass:`pi`,`emonpi2016`

change it here: `/etc/openhab/configurations/users.cfg`