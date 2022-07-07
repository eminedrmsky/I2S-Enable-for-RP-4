# I2S-Enable-for-RP-4
I2S sound devices do not supported by ALSA. In order to enable I2S interface on Raspberry Pi, first look at os properties;

```
$ cat /etc/os-release
PRETTY_NAME="Raspbian GNU/Linux 10 (buster)"
NAME="Raspbian GNU/Linux"
VERSION_ID="10"
VERSION="10 (buster)"
VERSION_CODENAME=buster
ID=raspbian
ID_LIKE=debian
HOME_URL="http://www.raspbian.org/"
SUPPORT_URL="http://www.raspbian.org/RaspbianForums"
BUG_REPORT_URL="http://www.raspbian.org/RaspbianBugs"
```

Then, enable I2S in device tree by uncommenting "#dtparam=i2s=on" in "/boot/config.txt".

```
$ sudo nano /boot/config.txt

```
Add "snd-bcm2835" to the "/etc/modules",

```
$ sudo nano /etc/modules

```
Reboot the Raspberry Pi by using,
```
$ sudo reboot

```
Then, make sure that modules are loaded

```
$ lsmod | grep snd 

```
You must get something like this


will continue ...
