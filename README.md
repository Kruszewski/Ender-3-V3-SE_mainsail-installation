# Ender-3-V3-SE_mainsail-installation
Guide for installation of mainsail on Ender 3 V3 SE

[MainsailOS](https://docs.mainsail.xyz/)
[Klipper](https://www.klipper3d.org/)

## What you will need:
- raspberry pi
- micro sd card for raspberry pi
- sd card for 3D printer update
- 3D printer (suprise!)

### 1. Install MainsailOS throught Raspberry Pi imiger on yout RaspberryPi
<img width="678" alt="zrzut_ekranu 2023-10-24 o 22 46 56" src="https://github.com/Kruszewski/Ender-3-V3-SE_mainsail-installation/assets/58085942/76ae2dc6-adee-4b42-9ac3-5c452a7dcff5">

- Head to ```Other specific-purpose OS```
- Select ```3D printing``` and then ```Mainsail OS``` (32 bit version is recommended)
- Choose your storage
- Enable SSH
- Set your username and password

> [!NOTE]
> Default username: **pi**, password: **raspberry**
  
### 2. Build and flash micro-controler


Run this commands on RaspberryPi:
```
cd ~/klipper/
make menuconfig
```

When text-based window opens select:
- ```STM32F103``` with a ```28KiB bootloader``` and serial **(on USART1 PA10/PA9)**
### 3. Use SCP protocol to download **klipper.bin** file to your computer.

```
pwd
scp remote_username@ip-adress:/remote/klipper.bin /local/directory
```
*pwd* - displays your current directory

Using defult settings:
```remote_username``` is **pi**

### 4. Upload ```klipper.bin``` to SD card and plug it into your printer. Connect RaspberryPi to 3D printer.
### 5. Head to RaspberryPi IP adress or use default hostname ```http://mainsailos(.local)```
### 6. Upload ```printer.cfg``` file in the settings tab.
### 7. You are ready to go!








## **Source**
- https://github.com/0xD34D/ender3-v3-se-klipper-config/tree/main
- https://linuxize.com/post/how-to-use-scp-command-to-securely-transfer-files/
- https://www.klipper3d.org/
- https://docs.mainsail.xyz/
