## [BlackUSB](http://www.maravento.com/p/blackusb.html)

[![License](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl.txt)
[![GitHub version](https://img.shields.io/badge/Version-1.0-yellowgreen.svg)](http://www.maravento.com/p/blackusb.html)

**BlackUSB** es un script experimental, que previene el robo de datos personales, malware, herramientas forenses, BadUSB (USB Rubber Ducky), etc. Genera una lista blanca de dispositivos usb/hid y bloquea cualquier otra inserción no autorizada de dispositivos desconocidos, usando reglas udev

**BlackUSB** is a experimental script, that prevents theft of personal data, malware, forensic tools, BadUSB (USB Rubber Ducky), etc. Generates a whitelist of usb/hid devices and blocks any other unauthorized insertion of unknown devices, using udev rules.

### BLACKUSB LINUX
---

Es un bash script que genera una lista blanca de dispositivos usb/hid y bloquea cualquier otra inserción no autorizada de dispositivos desconocidos, usando reglas udev

It is a bash script that generates a white list of usb/hid devices and blocks any other unauthorized insertion of unknown devices, using udev rules

```
sudo wget -q -N https://github.com/maravento/blackusb/raw/master/blackusb -O /etc/init.d/blackusb
```

##### Modo de Uso / How to Use

Example:

`blackusb show` or `blackusb s`

```
sudo /etc/init.d/blackusb s
 0 Name=xHCI Host Controller, Vendor=1d6b, Product=0003, Serial=0022:00:14.0
 1 Vendor=8087, Product=07dc
 2 Name=USB2.0-CRW, Vendor=0bda, Product=0129, Serial=20100001396000000
 3 Name=Integrated_Webcam_HD, Vendor=0c45, Product=6710
 4 Name=HID-compliant mouse, Vendor=046d, Product=c530
 5 Name=xHCI Host Controller, Vendor=1d6b, Product=0002, Serial=0022:00:14.0
```

##### Ficha Técnica / Data Sheet

|Full|Short|Description|
|----|-----|-----------|
|show|s|Muestra los dispositivos conectados / Show currently connected usb devices|
|on|o|Activar blackusb y genera lista blanca de dispositivos USB conectados / Turn on blackusb and generate white list of connected USB devices|
|eject|j|Elija un dispositivo de la lista para expulsarlo o agregar entrada/Choose a device from the list to eject or add entry|
|off|x|Desactiva temporalmente blackusb / Temporarily deactivate blackusb|
|gen|g|Genera o refresca lista blanca de dispositivos lista udev usb / Generate or refresh whitelist udev rules file|
|del|d|Elimina archivo udev que contiene lista blanca de dispositivos usb / Delete udev rules file contain white list usb devices|
|edit|e|Edita manualmente las reglas udev / Edit udev rules file manually|

##### Modo Paranoico / Paranoic Mode

Consiste en apagar su terminal cuando se inserte un dispositivo usb no autorizado y/o desconocido, en lugar de bloquearlo. Para activarlo, edite manualmente el script y descomente la línea

It consists of turning off your terminal when inserting an unauthorized and/or unknown usb device, rather than locking it. To activate it, edit the script manually and uncomment the line

`'poweroff'`

##### Logs

`/var/log/blackusb.log`

Example:

```
2017-07-06 12:34:10 Blackusb triggered!
Unknown Device Blocked: SUBSYSTEM=="usb", ATTR{idVendor}=="0781", ATTR{idProduct}=="5567", ATTR{serial}=="4C530799910104103543"
Cruzer Blade
```

##### Dependencias / Dependencies

`bash`, `udev`

##### Bifurcación / Fork

Este proyecto está basado en: / This project is based on:

[usbkill](https://github.com/hephaest0s/usbkill)

[usbdeath](https://github.com/trpt/usbdeath)

##### Licence

[GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.en.html)

### BLACKUSB WINDOWS
---

Es una herramienta que cuenta dos versiones. Standard (S) y Deep (D). La version "Standard", limpia las conexiones previas de dispositivos USB/HID, re-escanea los conectados y bloquea los nuevos dispositivos USB/HID (no autorizados), por tanto es un proceso rápido. La version "Deep", realiza una limpieza más profunda de instalaciones previas USB/HID y reinstala nuevamente los drivers de dispositivos USB/HID conectados, por tanto es más lenta que la "Standard"

It is a tool that counts two versions. Standard (S) and Deep (D). The "Standard" version, clean the previous connections of USB/HID devices, re-scan the connected ones and block the new USB/HID devices (not authorized), therefore it is a fast process. The "Deep" version performs a more thorough cleaning of previous USB/HID installations and reinstalls the drivers of connected USB/HID devices, so it is slower than the "Standard"

##### Descarga / Download

[![Image](https://1.bp.blogspot.com/-Y_vVfquMvAE/WsOHgH6kY1I/AAAAAAAAD6Q/PPbPjbEBHH4YJDrcU6tE0ENbhHMroAmRQCLcBGAs/s1600/quick-download.png)](https://github.com/maravento/blackusb/raw/master/win/BlackUSB.zip)

##### Ficha Técnica / Data Sheet

|File|Version|OS|Update|Size|
|----|-------|--|------|----|
|BlackUSB.exe (.zip)|1.0|Windows 7/8/10 x86 x64|Ago 10/2017|2,45 MB|

##### Descarga / Download (Deep Version)

[![Image](https://1.bp.blogspot.com/-Y_vVfquMvAE/WsOHgH6kY1I/AAAAAAAAD6Q/PPbPjbEBHH4YJDrcU6tE0ENbhHMroAmRQCLcBGAs/s1600/quick-download.png)](https://github.com/maravento/blackusb/raw/master/win/BlackUSBD.zip)

##### Ficha Técnica / Data Sheet (Deep Version)

|File|Version|OS|Update|Size|
|----|-------|--|------|----|
|BlackUSBD.exe (.zip)|1.0|Windows 7/8/10 x86 x64|Jul 12/2017|4,75 MB|

##### Modo de Uso / How to Use

- Desactive su Antivirus, Antimalware, SmartScreen o cualquier otra solución de seguridad en su Sistema Operativo y cierre todas las ventanas / Disable your Antivirus, Antimalware, SmartScreen or any other security solution in your Operating System and close all windows
- Descargue BlackUSB.exe (.zip) o BlackUSBD.exe (.zip), descomprimirlo en el escritorio / Download BlackUSB.exe (.zip) or BlackUSBD.exe (.zip), unzip it on your desktop
- Ejecútelo con doble clic, acepte la ejecución con privilegios y siga las instrucciones en pantalla / Run Setup by double-clicking accept execution with privileges and follow the onscreen instructions

##### Importante Antes de Usar / Important Before Use

- No pulse el botón **BLOCK**, dos veces seguidas, o bloqueará todos los dispositivos USB/HID / Do not press **BLOCK** button twice in a row or it will block all USB/HID devices.
- Si tiene establecidas [políticas GPO](https://es.wikipedia.org/wiki/Directiva_de_Grupo) en su sistema, serán reescritas. Haga backup GPO antes de usar BlackUSB / If you have defined [GPO policies](https://en.wikipedia.org/wiki/Group_Policy) on your system, they will be rewritten. Make a GPO backup before using BlackUSB
- Para incorporar un nuevo dispositivo USB/HID a su lista blanca (excluidos de bloqueo) debe pulsar el botón RESTORE para eliminar las restricciones, luego conectar el nuevo dispositivo y finalmente pulsar  el botón BLOCK / To add a new USB/HID device to your whitelist (excluded from blocking) you must press the RESTORE button to remove the restrictions, then connect the new device and finally press BLOCK button
- Despues de ejecutar la opción BLOCK, aparecerá en su escritorio el archivo de reporte **whiteusb.txt**, que contiene la lista blanca de dispositivos USB/HID excluidos del bloqueo. Esta lista será eliminada al utilizar la opción RESTORE / After executing the BLOCK option, the **whiteusb.txt** report file, which contains the white list of USB/HID devices excluded from the lock, will be displayed on your desktop. This list will be deleted when using the RESTORE option
- BlackUSB para Windows está incluido en [Dextroyer](http://www.dextroyer.com) / BlackUSB for Windows is included in [Dextroyer](http://www.dextroyer.com)

### CONTRIBUCIONES / CONTRIBUTIONS
---

Agradecemos a todos los que han contribuido con este proyecto / We thank all those who contributed to this project. Special thanks Novatoz.

### DONACION / DONATE
---

BTC: 3M84UKpz8AwwPADiYGQjT9spPKCvbqm4Bc

### LICENCIA / LICENCE
---

#####  Public

[GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.en.html), [Gnome Zenity](https://wiki.gnome.org/Projects/Zenity)

#####  Copyright (To some programs used to build BlackUSB for Windows)

[Jpsoft](https://jpsoft.com/), [Indigo Rose](https://www.indigorose.com/autoplay-media-studio/), [SteelWerX](https://fstaal01.home.xs4all.nl/swreg-us.html), [Microsoft](https://www.microsoft.com/), [74cz](http://74.cz/es/make-sfx/index.php), [Resource Hacker](http://www.angusj.com/resourcehacker/), [HashGenerator](http://www.SecurityXploded.com), [USBOblivion](https://sourceforge.net/projects/usboblivion/), [robvanderwoude](http://www.robvanderwoude.com/)

[![License](https://licensebuttons.net/l/by-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-sa/4.0/)
[maravento.com](http://www.maravento.com), [gateproxy.com](http://www.gateproxy.com) and [dextroyer.com](http://www.dextroyer.com) is licensed under a [Creative Commons Reconocimiento-CompartirIgual 4.0 Internacional License](http://creativecommons.org/licenses/by-sa/4.0/).

© 2018 [Maravento Studio](http://www.maravento.com)

### EXENCION DE RESPONSABILIDAD / DISCLAIMER
---

Estos scripts puede dañar su sistema si se usan incorrectamente. Úselos bajo su propio riesgo / This scripts can damage your system if used incorrectly. Use it at your own risk.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
