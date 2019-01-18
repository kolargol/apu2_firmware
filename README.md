# PC Engines APU2 Custom firmware with AMD Microcode
This is mirror repository for my APU2 firmware builds that include [AMD microcode](https://github.com/platomav/CPUMicrocodes)  
Build are made using official [build process](https://github.com/pcengines/apu2-documentation/blob/master/docs/microcode_patching.md).  AMD microcode cannot be included in official build as AMD licence prohibits its usage.  
New microcode contains Spectre mitigations - Indirect Branch Prediction Barrier (IBPB)  
  
**Use on your own risk.**  
  
If you do not understand any of this please [use official firmware](https://pcengines.github.io/) build by professionals from [3mdeb](https://3mdeb.com/about-us/)  
  
For my custom builds read more on: https://blog.onefellow.com/
## How to flash APU
1) Install https://www.flashrom.org/
2) If you are running OpenBSD: ```echo "sysctl kern.securelevel=-1" > /etc/rc.securelevel```,reboot
3) Become root
4) Download binary from *firmware/* and coresponding .asc file
5) Import my public GPG key from https://onefellow.com/
6) Verify if binary is correct (```gpg2 --verify xxxx.sig```)
7) FLASH: ```flashrom -w apu2_vX.X.X-FX.rom  --programmer internal:boardmismatch=force```  
you can remove **boardmismatch=force** if you are already running new firmware branch
8) Reboot: Remember that after flashing boot order is reset so you have to change it during reboot (F10)
9) On OpenBSD if all OK, remove ```/etc/rc.securelevel``` and reboot  


If you need build for your APU please make a request via [Issues](https://github.com/kolargol/apu2_firmware/issues)
