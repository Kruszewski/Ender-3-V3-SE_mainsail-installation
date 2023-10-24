# Ender-3-V3-SE_mainsail-installation
Repository for instalation of mainsail on Ender 3 V3 SE

[MainsailOS](https://docs.mainsail.xyz/)
[Klipper](https://www.klipper3d.org/)

1. Install MainsailOS throught Raspberry Pi imiger on yout RaspberryPi
<img width="678" alt="zrzut_ekranu 2023-10-24 o 22 46 56" src="https://github.com/Kruszewski/Ender-3-V3-SE_mainsail-installation/assets/58085942/76ae2dc6-adee-4b42-9ac3-5c452a7dcff5">

- Head to ```Other specific-purpose OS```
- Select ```3D printing``` and then ```Mainsail OS``` (32 bit version is recommended)
- Choose your storage
- Enable SSH
- Set your username and password ```Default username: **pi**, password: **raspberry**``` 

  
3. Build and flash micro-controler


Run this commands on RaspberryPi:
```
cd ~/klipper/
make menuconfig
``` 
3. Use SCP protocol to download **klipper.bin** file to your computer.

```
scp remote_username@10.10.0.2:/remote/file.txt /local/directory
```
5. Upload ```**klipper.bin**``` to SD card and plug it into your printer. Connect RaspberryPi to 3D printer.
6. Head to RaspberryPi IP adress or use default hostname ```http://mainsailos(.local)```
7. Upload ```printer.cfg``` file in the settings tab.
8. You are ready to go!




**Source**
- https://github.com/0xD34D/ender3-v3-se-klipper-config/tree/main
- https://linuxize.com/post/how-to-use-scp-command-to-securely-transfer-files/
- https://www.klipper3d.org/
- https://docs.mainsail.xyz/
