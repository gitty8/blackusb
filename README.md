## BlackUSB

<a target="_blank" href=""><img src="https://img.shields.io/badge/Development-ALPHA-blue.svg"></a>

Blackusb es un bash script que genera una lista blanca de dispositivos usb y bloquea cualquier otra inserción no autorizada de dispositivos usb desconocidos, usando reglas udev. Es ideal para prevenir herramientas forenses, BadUSB (USB Rubber Ducky), robo de datos, configuraciones y contraseñas en su servidor o terminal, así como introducción de malware vía usb / Blackusb is a bash script that generates a white list of usb devices and blocks any other unauthorized insertion of unknown usb devices, using udev rules. It is ideal for preventing forensic tools, BadUSB (USB Rubber Ducky), data theft, configurations and passwords on your server or terminal, as well as introducing malware via usb.

### Path
`/etc/init.d`

### Modo de Uso/How to use
`blackusb action`

e. g.: `blackusb show` or `blackusb s`

### Descripción/Description

|Full|Short|Description|
|----|-----|-----------|
|show|s|Muestra los dispositivos conectados / show currently connected usb devices|
|on|o|Activar blackusb y genera lista blanca de dispositivos USB conectados / Turn on blackusb and generate white list of connected USB devices|
|eject|j|Elija un dispositivo de la lista para expulsarlo o agregar entrada/Choose a device from the list to eject or add entry|
|off|x|Desactiva temporalmente blackusb / temporarily deactivate blackusb|
|gen|g|Genera o refresca lista blanca de dispositivos lista udev usb / Generate or refresh whitelist udev rules file|
|del|d|Elimina archivo udev que contiene lista blanca de dispositivos usb / Delete udev rules file contain white list usb devices|
|edit|e|Edita manualmente las reglas udev / Edit udev rules file manually|

### Paranoic Mode
Consiste en apagar su terminal cuando se inserte un dispositivo usb no autorizado y/o desconocido, en lugar de bloquearlo. Para activarlo, edite manualmente el script y descomente la línea / It consists of turning off your terminal when inserting an unauthorized and / or unknown usb device, rather than locking it. To activate it, edit the script manually and uncomment the line

`'poweroff'`

### Logs

`/var/log/blackusb.log`

format:

`2016-09-13 08:27:10 blackusb triggered! idVendor: 1d6b, idProduct: 0003, iProduct: xHCI?Host?Controller`

### Dependencias/Outbuildings

`bash`, `udev`

### Source

Blackusb está basado en: / Blackusb is based on:

[usbkill](https://github.com/hephaest0s/usbkill)

[usbdeath](https://github.com/trpt/usbdeath)

#### Disclaimer

Este script puede dañar su sistema si se usa incorrectamente. Úselo bajo su propio riesgo. This script can damage your system if used incorrectly. Use it at your own risk.
