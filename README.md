# Arduino for Quectel BC66 LTE Narow Band modules 
( OpenCPU based )

**A few words in the beginning**
* This project not an official product of Quectel / Mediatek
* The project is based on Quectel OpenCPU and port must be work on all NB modules
* Quectel modules BC66NA will not be supported, your module must be marked as BC66NB-
* Quectel BC26 should work ( with small modifications maybe, I do not have a module for experiments )
* The full/exended port will make later, this will be start base
* License: Free for all
* This compile version: 1.0.3


**Chipset Mediatek MT2625 SoC**
Ultra-low power, 3GPP Release-14 enabled NB-IoT platform for wide-ranging home, civic, industrial or mobile applications
https://www.mediatek.com/products/nbIot/mt2625


**Module: Quectel BC66**
is a high-performance, multi-band NB-IoT module...
https://www.quectel.com/product/bc66.htm
* Test Board for the project: BC66-TE-B ( it is shield Arduino, unfortunately... )
* Modules BC66NA... is obsolete, replace with BC66NB... and firmware for NB
* API: OpenCPU, native C, EAT (Embedded AT) oriented
* User Application Size: ROM (BIN) 200k, RAM 100k

![ScreenShot](https://raw.githubusercontent.com/Wiz-IO/Arduino_MT2625_BC66/master/board.jpg)

**Tools**
* Arduino IDE (Windows for now)
https://www.arduino.cc/
* Firmware, USB Drivers, Quectel IoT Flash Tool
https://app.box.com/s/3wrkh1yzn09yuyb5f8v5vllmlir0571s
* MQTT test monitor 
http://quectel.slimfitdesign.com/nb-iot/mqtt/

![ScreenShot](https://raw.githubusercontent.com/Wiz-IO/Arduino-Quectel-BC66/master/images/arduino.png)

TCP Client example log
```
Leaving the BROM
[DBG] READY
[DEV] Quectel EXTENDED API BC66NBR01A04
[DBG] CPU Frequency: 78000000 Hz
[ARDUINO] Begin
[DEV] MSG_ID_RIL_READY
[APP] Socket Example
[IMEI] 867997030026503
[BAND] AT+QBAND=1,3, rc = 0
[RIL] MSG_ID_URC_INDICATION: 2, 1
[RIL] MSG_ID_URC_INDICATION: 5, 2
[RIL] MSG_ID_URC_INDICATION: 5, 1
[APP] Narrow Band Level: -89,
[APP] DNS wizio.eu = 193.107.36.200
[SOC] Conecting...
[SOC] Conected: 0
HTTP/1.1 200 OK
Date: Thu, 11 Oct 2018 10:39:18 GMT
Server: Apache/2.4.23 (Win32) OpenSSL/1.0.2j PHP/5.6.26
X-Powered-By: PHP/5.6.26
Content-Length: 37
Content-Type: text/html; charset=UTF-8
[APACHE] Hello World ( 2018/10/11 )
[SOC] Close
[APP] waithing...
......
Test Result...
LTE Narrow Band 3 (1800 MHz)
LWIP Socket, HTTP-GET
180 minutes, 180 packets (240 bytes), 1 minute interval
RX: -95 dBm, 1814.31 MHz 
TX: +21 dBm, 1723.08 MHz
PACKET LOST: 0
```

**ATTENTION: Before start exeriments:**
* Update firmware version
* Make Backup of NVDM Fields (module "eeprom")
* IoT Tool, [Backup] button, check-box "Backup", select file for backup (use IMEI as name), [Start] and keep the file
* Now you can start all and you can restore the module if need
* Note: if you upload application to module you lose standart AT command via uarts (with backup file you can restore this)


**Install**

* Add json link to Arduino - Preferences 

http://wizio.eu//arduino/bc66/package_wizio.bc66_index.json

* Open Borad Manager, Find WizIO, Install, Select board, Click [Compile] or [Upload]


**Thanks to**

* Radu Igret for terminal uploader


TODO:
* add SPI
* add I2S
* add all gpio-s
* debug and other stufs
* Arduino + Extended API gives you tremendous opportunities for LTE Narrow Band

The extended API is dependent on firmware version.
The API support direct calls to the core as FreeRTOS, lvip, mbedtls, http, mqtt...etc.
API is selected as board model in Arduino Menu - Boards Manager.

Example: Quectel BC66NB-TE-B < R01A04V01 >

This api/board is dependent with firmware BC66NBR01A04V01 and module must be updated with this version.
API has soft protection of not correct versions.
Is in development... I need a few free days to add base...



**If you want to help / support - contact me**

# Other - Comming soon....
