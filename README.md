[![](https://img.shields.io/badge/Telegram-HackintoshLifeIT-informational?style=flat&logo=telegram&logoColor=white&color=5fb659)](https://t.me/HackintoshLife_it)
[![](https://img.shields.io/badge/Facebook-HackintoshLifeIT-informational?style=flat&logo=facebook&logoColor=white&color=3a4dc9)](https://www.facebook.com/hackintoshlife/)
[![](https://img.shields.io/badge/Instagram-HackintoshLifeIT-informational?style=flat&logo=instagram&logoColor=white&color=8a178a)](https://www.instagram.com/hackintoshlife.it_official/)

# H270 MSI GAMING M3 + I5 7600 + Thunderbolt 3 GC Titan Ridge

EFI H270 MSI GAMING M3 +I5 7600 with OpenCore bootloader

![descrizione](./Infos/pc.png)

# The Motherboard don't have anythings related to Thunderbolt 3 but with our group we make it works :sunglasses: Just hotplug is WIP

### Computer Spec:

| Component        | Brank                                  |
| ---------------- | ---------------------------------------|
| CPU              | Intel i5-7600                          |
| iGPU             | Intel® Graphics HD 630 (HEADLESS PATCH)|
| dGpu             | Sapphire pulse RX 580 8 GB             |
| Audio            | Realtek ALC1220                        |
| Ram              | 32 GB Corsair Vengeance                |
| Wifi + Bluetooth | Fenvi t919                             |
| Lan              | Killer™ E2500 Gigabit LAN              |
| Thunderbolt 3    | GC Titan Ridge V2                      |
| NVMe             | Samsung 970 evo plus 1TB ( MacOS)      |
| SSD Sata         | Kingston SSD 1TB (Windows)             |
| SSD Sata         | Kingston a400 2 TB (shared storage)    |
| SmBios           | iMac 18,3                              |
| BootLoader       | OpenCore 0.6.6                         |
| macOS            | Big Sur 11.1                           |



![infobigsur](./Infos/infomac.png)


### What works and What doesn't or WIP:

- [x] CFG Unlock
- [x] Intel Graphics UHD iGPU (use for task only)
- [x] ALC1220 All jack activate
- [x] ALC1220 Combo jack external
- [x] All USB 3.1 Ports (ASM2142 controller)
- [x] Sleep / Wake
- [x] Wi-Fi and Bluetooth
- [x] Controller SATA III
- [x] Controller NVME PciE Gen3x4 
- [x] All Sensors CPU, IGPU, GPU, NVME, SATA, FAN
- [x] Apple VTD
- [x] NVRAM
- [x] Recovery (macOS) boot from OpenCore
- [x] Windows 10 boot from OpenCore
- [x] Thunderbolt 3 GC Titan Ridge V2
- [ ] Hotplug for GC Titan Ridge

## Peripherals & Benchmarks

![infohack](./Infos/peripherals.png)
![infopci](./Infos/TB.png)
![CPU](./Infos/cputest.jpg)
![metal](./Infos/metal.jpg)
![opencl](./Infos/opencl.jpg)
![videoproc](./Infos/videoproc.png)

# Bios settings
# BIOS VERSION E7A62IMS.270 BUILD DATE 07/03/2018

## Disable cfg lock

To disable cfg lock use the provided kit.

In the folder is provided a dump of BIOS E7A62IMS.270 version for references. 

**THANKS TO [LORYS89](https://github.com/Lorys89) for the hints, BIOS dump and the kit**

Declare tools in config.plist

Reboot the system, when you are at Opencore run modGRUBShell.efi


Type `setup_var 0x526`to interrogate, the result is `Offset 0x526 is: 0x01` this mean that the cfg lock is enabled

Then type `setup_var 0x526 0x00`to write, the result is `Offset 0x526 is: 0x01 setting offset 0x526 to 0x00` this mean that the cfg lock is disabled

Type `EXIT` to return to Opencore Bootloader, Reset nvram and use VerifyMsrE2.efi to check if the cfg lock is disabled.

XMP **[OFF]**

### SETTINGS\ADVANCED
#### PCI Subsystem Settings

PEG0 - Max Link Speed **[Auto]**
PCI Latency Timer **[32 PCI Bus Clock]**
Above 4g memory/Crypto Currency **[Disabled]**

#### ACPI Settings
Power LED **[Blinking]**

#### Integrated Peripherals
Onboard LAN Controller **[Enabled]**
LAN Option ROM **[Disabled]**
Network stacks **[Disabled]**

SATA Mode **[AHCI Mode]**
M.2/Optane Genie **[Disabled]**
SATA 1|6 Hot Plug **[Disabled]**


HD Audio Controller **[Enabled]**

HPET **[Enabled]**

Intel Serial I/O **[Disabled]**

#### Integrated Graphics Configuration
##### I use an headless patch for iGPU just for Apple continuity services
Initiate Graphics Adapter **[PEG]**
Integrated Graphics Share Memory **[128M]**
IGD Multi-Monitor **[Enabled]**
 
#### USB Configuration
USB Controller **[Enabled]**
XHCI Hand-off **[Enabled]**
Legacy USB Support **[Enabled]**

#### Super IO Configuration\ (COM) Port 0 configration
Serial(COM) Port0 **[Enabled]**
Serial(COM) Port= Settings **[Auto]**

#### Power Management Setup
ErP Ready **[Disabled]**
Restore after AC Power Loss **[Power off]**
System Power Fault Protection **[Disabled]**

#### Windows OS Configuration
Windows 8.1/10 WHQL Support **[Disabled]**
Windows 7 Installation **[Disabled]**
MSI Fastboot **[Disabled]**
Fast Boot **[Disabled]**

#### Wake Up Event Setup
Setup Wake Up Configuration **[Bios]** 
Resume By RTC Alarm **[Disabled]**
Resume By PCI-E Device **[Disabled]**
Resume By USB device **[Enabled]**
Resume From S3/S4/S5 by PS/2 mouse **[Disabled]**
Resume From S3/S4/S5 by PS/2 keyboard **[Disabled]**



### Special Config

- Usb port mapping performed
- Add ASMEDIA 2142 controller Kext
- SSDT-Hack Essential patch
- SSDT for GC Titan Ridge V2
- Drom flash for GC Titan Ridge V2

See [IOREG](https://github.com/basett1/HACKINTOSH-MSI-H270-OPENCORE/blob/main/iMac.ioreg) for infos

## Credits

- [Apple](https://apple.com) for macOS.
- [Acidanthera](https://github.com/acidanthera) for OpenCore and all the lovely hackintosh work.
- [Dortania](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/icelake.html) For great and detailed guides.
- [Hackintoshlifeit](https://github.com/Hackintoshlifeit) Support group for installation and post installation.
- [Lorys89](https://github.com/Lorys89) for the continuous support and for the cfg lock tools and info
- [MBarbierato](https://github.com/mbarbierato) for the support and the infos about thunderbolt
- Caseysj for the thunderbolt nvm50 thunderbolt DROM

# If you need help please contact us on [Telegram](https://t.me/HackintoshLife_it) or [Web](https://www.hackintoshlife.it/)

