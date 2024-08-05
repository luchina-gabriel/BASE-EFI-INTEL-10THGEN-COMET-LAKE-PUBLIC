# BASE EFI Intel Comet Lake, Coffee Lake Plus and Ice Lake

# 🛠️ Remote Services | Serviços remotos

🇺🇸 - If you wish, we can create your EFI and [install macOS remotely](https://universohackintosh.com/portal/consultoria-profissional-para-hackintosh/#servico-instalacao-completa-do-hackintosh), just hire our services via the email below.
<br>
🇧🇷 - Se desejar, criamos sua EFI e realizamos a [instalação remotamente do macOS](https://universohackintosh.com/portal/consultoria-profissional-para-hackintosh/#servico-instalacao-completa-do-hackintosh), basta contratar nossos serviços pelo e-mail abaixo.
<br>
✉️ - Endereço EXCLUSIVO para contratação de serviços: consultoria@universohackintosh.com.br.

# 🆘 How to GET a COPY of BASE EFI <br> 🆘 Como obter a CÓPIA da EFI BASE

🇺🇸 - To download EFI BASEs, you must be a member of any category on the [YouTube Channel](https://hackintosh.one/s/seja-membro) and connect your Discord to your YouTube account to access the [#efi-base](https://discord.com/channels/887798875069505587/1184144798312038512) channel;
<br><br>
🇧🇷 - Para download das EFIs BASEs, é necessário você ser membro de qualquer categoria no [Canal do YouTube](https://hackintosh.one/s/seja-membro) e conectar seu Discord à sua conta YouTube para acesso à sala [#efi-base](https://discord.com/channels/887798875069505587/1184144798312038512);

![youtube_connection](https://github.com/luchina-gabriel/BASE-EFI-INTEL-DESKTOP-10THGEN-COMET-LAKE-PUBLIC/assets/23700365/cfd72190-60b2-4158-b4b8-73fad7c4139e)
<br>
![efi-base-channel](https://github.com/luchina-gabriel/BASE-EFI-INTEL-DESKTOP-10THGEN-COMET-LAKE-PUBLIC/assets/23700365/7a622247-e691-4820-b5ce-b2ed53b7fd3e)

# Basic Info

Note|Description
:----|:----
Initial macOS Support|macOS 10.15, Catalina.
Last Supported OS|macOS 15 Sequoia.

- Opencore version: 1.0.1
- Release date: 05/08/2024

# Basic Steps

1. [Download](https://discord.com/channels/887798875069505587/1184144798312038512) the latest release [Discord, #efi-base channel];
2. Includes **additional** kexts (for ethernet, audio, etc);
3. Include the **necessary** ACPI patches (.aml);
4. Review the special notes;
5. Generate and complete your SMBIOS infos - **ALWAYS**;
6. Adjust your BIOS;
7. Install macOS and enjoy :)

# Features
- [x] Very light, very clean, basic files for your Hackintosh.
- [x] Made with latest OpenCore versions.
- [x] Two editions - *Release* and *Debug* Edition.
- [x] Updated montly with refresh versions of Opencore.

# Kexts included (**Required**)

Kext|Description
:----|:----
[Lilu.kext](https://github.com/acidanthera/Lilu/releases)|Patch many processes, required for AppleALC, WhateverGreen, VirtualSMC and many other kexts.
[SMCProcessor.kext](https://github.com/acidanthera/VirtualSMC/releases)|Used for monitoring CPU temperature, doesn't work on AMD CPU based systems.
[SMCSuperIO.kext](https://github.com/acidanthera/VirtualSMC/releases)|Used for monitoring fan speed, doesn't work on AMD CPU based systems.
[VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC/releases)|Emulates the SMC chip found on real macs, without this macOS will not boot.<br>Alternative is FakeSMC which can have better or worse support, most commonly used on legacy hardware.
[WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen/releases)|Used for graphics patching, DRM fixes, board ID checks, framebuffer fixes, etc; all GPUs benefit from this kext.

# Other Kexts (not included)

Kexts for support Audio, Wifi, Ethernets and other devices.

### Audio

Kext|Description
:----|:----
[AppleALC.kext](https://github.com/acidanthera/AppleALC/releases)|Used for AppleHDA patching, allowing support for the majority of on-board sound controllers.<br>AMD 15h/16h may have issues with this and Ryzen/Threadripper systems rarely have mic support.
[VoodooHDA.kext](https://sourceforge.net/projects/voodoohda/)|Audio for FX systems and front panel Mic+Audio support for Ryzen system, do not mix with AppleALC.<br>Audio quality is noticeably worse than AppleALC on Zen CPUs.

### Ethernet
Kext|Description
:----|:----
[IntelMausi.kext](https://github.com/acidanthera/IntelMausi/releases)|Intel's 82578, 82579, I217, I218 and I219 NICs are officially supported.
[IntelMausiEthernet.kext](https://github.com/luchina-gabriel/youtube-files/raw/main/IntelMausiEthernet.kext-V2.5.3d4.zip)|Alternative for some I219 NICs. Use it if the kext above doesn't work.
[IntelMausiEthernet.kext](https://github.com/CloverHackyColor/IntelMausiEthernet/releases)|Some alternative for some I219 NICs. Use it if the kext above doesn't work.
[AtherosE2200Ethernet.kext](https://github.com/Mieze/AtherosE2200Ethernet/releases)|Required for Atheros and Killer NICs.<br>**Note**: Atheros Killer E2500 models are actually Realtek based, for these systems please use RealtekRTL8111 instead.
[RealtekRTL8100.kext](https://github.com/luchina-gabriel/youtube-files/raw/main/RealtekRTL8100-V2.0.1.zip)|Required for Realtek FE Familly Controller - 10/100 Mbps. Common on older hardware.
[RealtekRTL8111.kext](https://github.com/Mieze/RTL8111_driver_for_OS_X/releases)|Required for Realtek Gigabit Ethernet. Realtek GbE Familly Controller<br>Sometimes the latest version of the kext might not work properly with your Ethernet. If you see this issue, try older versions.
[LucyRTL8125Ethernet.kext](https://www.insanelymac.com/forum/files/file/1004-lucyrtl8125ethernet/)|Required for Realtek 2.5Gb Ethernet.
[SmallTreeIntel82576.kext](https://github.com/khronokernel/SmallTree-I211-AT-patch/releases)| Required for I211 NICs, based off of the SmallTree kext but patched to support I211.<br>Required for most AMD boards running Intel NICs.
[AppleIGB.kext](https://github.com/donatengit/AppleIGB/releases)|Required for I211 NICs running on macOS Monterey and above. Might have instability issues on some NICs, recommended to stay on Big Sur and use SmallTree. Requires macOS 12 and above.
[AppleIGC.kext](https://github.com/SongXiaoXi/AppleIGC/releases)|Required for I226 NICs running on macOS Monterey and above. Might have instability issues on some NICs.
[AppleIntelI210Ethernet.kext](https://github.com/luchina-gabriel/youtube-files/raw/main/AppleIntelI210Ethernet.kext.zip)|Required for Intel i225-V in macOS 12 (Monterey) and above.

### WiFi and Bluetooth
Kext|Description
:----|:----
[AirportItlwm](https://github.com/OpenIntelWireless/itlwm/releases)|Adds support for a large variety of INTEL WIRELESS cards and works natively in recovery thanks to IO80211Family integration.
[IntelBluetoothFirmware](https://github.com/OpenIntelWireless/IntelBluetoothFirmware/releases)|Adds Bluetooth support to macOS when paired with an Intel wireless card.
[AirportBrcmFixup](https://github.com/acidanthera/AirportBrcmFixup/releases)|Used for patching non-Apple/non-Fenvi Broadcom cards, will not work on Intel, Killer, Realtek, etc.<br>For Big Sur see [Big Sur Known Issues](https://dortania.github.io/OpenCore-Install-Guide/extras/big-sur#known-issues) for extra steps regarding AirPortBrcm4360 drivers.
[BrcmPatchRAM](https://github.com/acidanthera/BrcmPatchRAM/releases)|Used for uploading firmware on Broadcom Bluetooth chipset, required for all non-Apple/non-Fenvi Airport cards.

### USB
Kext|Description
:----|:----
[USBInjectAll](https://github.com/daliansky/OS-X-USB-Inject-All/releases)|Used for injecting Intel USB controllers on systems without defined USB ports in ACPI.<br>All Intel chipset series.<br>Requires OS X 10.11 or newer.
[XHCI-unsupported](https://github.com/daliansky/OS-X-USB-Inject-All/archive/refs/heads/master.zip)|Needed for non-native USB controllers.<br>Common chipsets needing this: H370, B360, H310, Z390(Not needed on Mojave and newer), X79, X99, AsRock boards(On Intel motherboards specifically, B460/Z490+ boards do not need it however).

### Others
Kext|Description
:----|:----
[NVMeFix](https://github.com/acidanthera/NVMeFix/releases)|Used for fixing power management and initialization on non-Apple NVMe.
[SATA-Unsupported](https://github.com/khronokernel/Legacy-Kexts/blob/master/Injectors/Zip/SATA-unsupported.kext.zip)|Adds support for a large variety of SATA controllers, mainly relevant for laptops which have issues seeing the SATA drive in macOS.<br>We recommend testing without this first.
[AppleMCEReporterDisabler](https://github.com/acidanthera/bugtracker/files/3703498/AppleMCEReporterDisabler.kext.zip)|Useful starting with Catalina to disable the AppleMCEReporter kext which will cause kernel panics on AMD CPUs.<br>Recommended for dual-socket systems (ie. Intel Xeons).
[RestrictEvents](https://github.com/acidanthera/RestrictEvents/releases)|Better experience with unsupported processors like AMD, Disable MacPro7,1 memory warnings and provide upgrade to macOS Monterey via Software Updates when available.
[CpuTscSync](https://github.com/acidanthera/CpuTscSync/releases)|It is a Lilu plugin, combining functionality of VoodooTSCSync and disabling xcpm_urgency if TSC is not in sync. It should solve some kernel panics after wake.
[SMDRadeonGPU](https://github.com/ChefKissInc/RadeonSensor)|Used for monitoring GPU temperature on AMD GPU systems. Requires RadeonSensor from the same repository. Requires macOS 11 or newer.
[FeatureUnlock](https://github.com/acidanthera/FeatureUnlock/releases)|Add Sidecar, NightShift, AirPlay, Universal Control and Continuity Camera support.

### Notebooks
Kext|Description
:----|:----
[VoodooPS2Controller](https://github.com/acidanthera/VoodooPS2/releases)|PS2 Keyboards/Trackpads.<br>Works with various PS2 keyboards, mice, and trackpads.<br>Requires macOS 10.11 or newer for MT2 (Magic Trackpad 2) functions.
[VoodooRMI](https://github.com/VoodooSMBus/VoodooRMI/releases)|SMBus Trackpads.<br>For systems with Synaptics SMBus trackpads.<br>Requires macOS 10.11 or newer for MT2 functions.<br>Depends on Acidanthera's VoodooPS2.
[VoodooSMBus](https://github.com/VoodooSMBus/VoodooSMBus/releases)|SMBus Trackpads.<br>For systems with ELAN SMBus Trackpads.<br>Supports macOS 10.14 or newer currently.
[VoodooI2C](https://github.com/VoodooI2C/VoodooI2C/releases)|I2C/USB HID Devices.<br>Attaches to I2C controllers to allow plugins to talk to I2C trackpads.<br>USB devices using the below plugins still need VoodooI2C.<br>Supports macOS 10.11+.
[ECEnabler](https://github.com/1Revenger1/ECEnabler/releases)|Fixes reading battery status on many devices (Allows reading EC fields over 8 bits long).<br>Supports OS X 10.7 and above (not needed on 10.4 - 10.6).
[BrightnessKeys](https://github.com/acidanthera/BrightnessKeys/releases)|Fixes brightness keys automatically.

# ACPI Tables, for Desktop

These files are **MUST** be included in your EFI's ACPI directory. We recommend that you use the **MANUAL** method, but for a first test you can use the prebuild versions.

SSDT|Description
:----|:----
SSDT-PLUG|[Manual](https://dortania.github.io/Getting-Started-With-ACPI/Universal/plug-methods/manual.html) \| [Prebuilt](https://github.com/dortania/Getting-Started-With-ACPI/raw/master/extra-files/compiled/SSDT-PLUG-DRTNIA.aml) \| [Details](https://dortania.github.io/Getting-Started-With-ACPI/Universal/plug.html)
SSDT-EC-USBX|[Manual](https://dortania.github.io/Getting-Started-With-ACPI/Universal/ec-methods/manual.html) \| [Prebuilt](https://github.com/dortania/Getting-Started-With-ACPI/raw/master/extra-files/compiled/SSDT-EC-USBX-DESKTOP.aml) \| [Details](https://dortania.github.io/Getting-Started-With-ACPI/Universal/ec-fix.html)
SSDT-AWAC|[Manual](https://dortania.github.io/Getting-Started-With-ACPI/Universal/awac-methods/manual.html) \| [Prebuilt](https://github.com/dortania/Getting-Started-With-ACPI/raw/master/extra-files/compiled/SSDT-AWAC.aml) \| [Details](https://dortania.github.io/Getting-Started-With-ACPI/Universal/awac.html)
SSDT-RHUB|[Manual](https://dortania.github.io/Getting-Started-With-ACPI/Universal/rhub-methods/manual.html) \| [Prebuilt](https://github.com/luchina-gabriel/youtube-files/raw/main/SSDT-RHUB.aml) \| [Details](https://dortania.github.io/Getting-Started-With-ACPI/Universal/rhub.html)

# ACPI Tables, for Notebook

SSDT|Description
:----|:----
SSDT-PLUG|[Manual](https://dortania.github.io/Getting-Started-With-ACPI/Universal/plug-methods/manual.html) \| [Prebuilt](https://github.com/dortania/Getting-Started-With-ACPI/raw/master/extra-files/compiled/SSDT-PLUG-DRTNIA.aml) \| [Details](https://dortania.github.io/Getting-Started-With-ACPI/Universal/plug.html)
SSDT-EC-USBX|[Manual](https://dortania.github.io/Getting-Started-With-ACPI/Universal/ec-methods/manual.html) \| [Prebuilt](https://github.com/dortania/Getting-Started-With-ACPI/blob/master/extra-files/compiled/SSDT-EC-USBX-LAPTOP.aml) \| [Details](https://dortania.github.io/Getting-Started-With-ACPI/Universal/ec-fix.html)
SSDT-AWAC|[Manual](https://dortania.github.io/Getting-Started-With-ACPI/Universal/awac-methods/manual.html) \| [Prebuilt](https://github.com/dortania/Getting-Started-With-ACPI/raw/master/extra-files/compiled/SSDT-AWAC.aml) \| [Details](https://dortania.github.io/Getting-Started-With-ACPI/Universal/awac.html)
SSDT-RHUB|[Manual](https://dortania.github.io/Getting-Started-With-ACPI/Universal/rhub-methods/manual.html) \| [Prebuilt](https://github.com/luchina-gabriel/youtube-files/raw/main/SSDT-RHUB.aml) \| [Details](https://dortania.github.io/Getting-Started-With-ACPI/Universal/rhub.html)
SSDT-PNLF|[Manual](https://dortania.github.io/Getting-Started-With-ACPI/Laptops/backlight-methods/manual.html) \| [Prebuilt](https://github.com/dortania/Getting-Started-With-ACPI/blob/master/extra-files/compiled/SSDT-PNLF.aml) \| [Details](https://dortania.github.io/Getting-Started-With-ACPI/Laptops/backlight.html)
SSDT-GPIO/XOSI|[Manual](https://dortania.github.io/Getting-Started-With-ACPI/Laptops/trackpad-methods/manual.html) \| [Prebuilt](https://dortania.github.io/Getting-Started-With-ACPI/Laptops/trackpad-methods/prebuilt.html) \| [Details](https://dortania.github.io/Getting-Started-With-ACPI/Laptops/trackpad.html)

### Dumping your DSDT in Windows Environment
[Download iASL Compiler ACPI Tools](https://www.intel.com/content/www/us/en/download/774881/acpi-component-architecture-downloads-windows-binary-tools.html)
<br><br>
Open the CMD in the directory where the *ACPI Tools* was extracted. (*Command Prompt*) in **Administrator Mode**:
```
path/to/acpidump.exe -b -n DSDT -z
move dsdt.dat DSDT.aml
```

Decompile DSDT.aml:
```
path/to/iasl.exe path/to/DSDT.aml
```
*File DSDT.dsl will generated. Use this for generate YOUR ACPI Patches.* 

Compile DSDT.dsl:
```
path/to/iasl.exe path/to/DSDT.dsl
```
*File APCPI_FILE_PATCHED.aml will generated.*

# Attention

Update **config.plist** in PlatformInfo > Generic with YOUR informations.
<br><br>
*1. MLB (Board Serial)
<br>
2. ROM (Mac Address)
<br>
3. SystemSerialNumber (Serial)
<br>
4. SystemUUID (SmUUID)*

Please use [*genSMBIOS*](https://github.com/corpnewt/GenSMBIOS/archive/refs/heads/master.zip) for generate values for above itens.
<br>
Please use [*ProperTree*](https://github.com/corpnewt/ProperTree/archive/refs/heads/master.zip) for configure/edit your config.plist.

# Compatible SMBIOS, for Desktop

SMBIOS|Description
:----|:----
iMac20,1|i7-10700K and lower(ie. 8 core and lower).
iMac20,2|i9-10850K and higher(ie. 10 core).

# Compatible SMBIOS, for Notebook

SMBIOS|Description
:----|:----
MacBookPro16,1|Hexa/Octa Core 45W,iGPU: UHD 630 + dGPU: 5300/5500M.
MacBookPro16,3|Quad Core 15W, iGPU: Iris 645.
MacBookPro16,4|Hexa/Octa Core 45W, iGPU: UHD 630 + dGPU: 5600M.	
MacBookPro16,2|Quad Core 28W,iGPU: G4/G7.
MacBookAir9,1|Dual/Quad Core 12W, iGPU: G4/G7.
Macmini8,1|NUC Systems, HD 6000/Iris Pro 6200.

# Catalina and older versions of macOS

- Please configure `MinDate` and `MinVersion` in UEFI > APFS to `-1`;
- Please configure `SecureBootModel` in Misc > Security to `j137`;

\* *Without above settings, macOS will not be able to boot.*

# macOS Sonoma 14.4 or above versions (including macOS Sequoia (v15))
- Please configure `SecureBootModel` to `Disabled`;
- After the installation is completed, you can return the value to 'Default';
- If the above adjustment is not performed, the installation will be in a looping.

# Special notes

- USB port mapping is **REQUIRED**.
- **`XhciPortLimit`** - Please `**ENABLE**` to map the USB ports
	- You can use USBMap.command Utility - [USBMap](https://github.com/corpnewt/USBMap).
- **`AppleXcpmCfgLock`** - Please **`ENABLE`** if you cannot disable`CFG-Lock` in BIOS.

# Special notes [DeviceProperties > Add]

- PciRoot(0x0)/Pci(0x2,0x0)
	- AAPL,ig-platform-id
		- 07009B3E - Replace AAAAAAAA. Used when the Desktop iGPU is used to drive a display.
		- 00009B3E - Replace AAAAAAAA. Alternative to `07009B3E` if it doesn't work.
		- 0300C89B - Replace AAAAAAAA. Used when the Desktop iGPU is only used for computing tasks and doesn't drive a display.
		- 0900A53E - Replace AAAAAAAA. Laptop, Recommended value for UHD 630.
		- 00009B3E - Replace AAAAAAAA. Laptop, Recommended value for UHD 620.
		- 07009B3E - Replace AAAAAAAA. NUC, Recommended value for UHD 620/630.
		- 0000A53E - Replace AAAAAAAA. NUC, Recommended value for UHD 655.
	- framebuffer-patch-enable - Uncomment if no BIOS options for iGPU memory.
	- framebuffer-stolenmem - Uncomment if no BIOS options for iGPU memory.

- PLEASE EDIT/ADD DEVICE FOR ETHERNET i225 (You can identify with Hackintool on `PCIe` tab).
	- If your board didn't ship with the Intel I225 NIC, there's no reason to add this entry.
	- If you get a kernel panic on the `AppleIntelI210Ethernet` kext, your Ethernet's path is likely `PciRoot(0x0)/Pci(0x1C,0x4)/Pci(0x0,0x0)`.
	- Please **`ENABLE`** Patch for i225 on `Kernel > Patch`.
	- for macOS Monterey 12.2.1 and below, please add `dk.e1000=0` in `boot-args`.
	- for macOS Monterey 12.3 or newer, please add `e1000=0` in `boot-args`.
	- for macOS Ventura, please add `e1000=0` in `boot-args` and add Kext [AppleIntelI210Ethernet.kext](https://github.com/luchina-gabriel/youtube-files/raw/main/AppleIntelI210Ethernet.kext.zip)

### GPU-Specific `boot-args`
Parameter|Description
:----|:----
agdpmod=pikera|Used for disabling board ID checks on Navi GPUs(RX 5000 series & RX 6000 series), without this you'll get a black screen.<br>**Don't use if you don't have Navi** (ie. Polaris and Vega cards shouldn't use this).
-wegnoegpu|Used for disabling all other GPUs than the integrated Intel iGPU, useful for those wanting to run newer versions of macOS where their dGPU isn't supported.

### Ethernet (Intel i225) `boot-args`
Parameter|Description
:----|:----
dk.e1000=0|Disables `com.apple.DriverKit-AppleEthernetE1000` (Apple's DEXT driver) from matching to the Intel I225-V Ethernet controller found on higher end Comet Lake boards, causing Apple's I225 kext driver to load instead.<br>This boot argument is optional on most boards as they are compatible with the DEXT driver. However, it is required on Gigabyte and several other boards, which can only use the kext driver, as the DEXT driver causes hangs.<br>You don't need this if your board didn't ship with the I225-V NIC.
e1000=0|for macOS 12.3.1 or newer<br>Disables `com.apple.DriverKit-AppleEthernetE1000` (Apple's DEXT driver) from matching to the Intel I225-V Ethernet controller found on higher end Comet Lake boards, causing Apple's I225 kext driver to load instead.<br>This boot argument is optional on most boards as they are compatible with the DEXT driver. However, it is required on Gigabyte and several other boards, which can only use the kext driver, as the DEXT driver causes hangs.<br>You don't need this if your board didn't ship with the I225-V NIC.

# BIOS Settings

### Disable
- Fast Boot
- Secure Boot
- Serial/COM Port
- Parallel Port
- VT-d (can be enabled if you set `DisableIoMapper` to YES)
- Compatibility Support Module (CSM).
- Thunderbolt(For initial install, as Thunderbolt can cause issues if not setup correctly)
- Intel SGX
- Intel Platform Trust
- CFG Lock (MSR 0xE2 write protection)
	- This must be off, if you can't find the option then **`ENABLE`** `AppleXcpmCfgLock`. 
	- Your hack will not boot with `CFG-Lock` enabled.

### Enable
- VT-x
- Above 4G decoding. 
	- This must be on, if you can't find the option then add `npci=0x2000` to `boot-args`. 
	- Do not have both this option and `npci` on `boot-args` enabled at the same time.
	- 2020+ BIOS Notes: When enabling Above4G, Resizable BAR Support may become an available on some Z490 and newer motherboards. Please ensure this is **`DISABLED`** instead of set to Auto.
- Hyper-Threading
- Execute Disable Bit
- EHCI/XHCI Hand-off
- OS type: Windows 8.1/10 UEFI Mode
- DVMT Pre-Allocated(iGPU Memory): 64MB
- SATA Mode: AHCI

# References
[Desktop, Comet Lake](https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html)
<br>
[Laptop, Coffee Lake Plus and Comet Lake](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake-plus.html)
<br>
[Laptop, Icelake](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/icelake.html)

## Discord - Universo Hackintosh
- [Access Discord](https://discord.universohackintosh.com.br)
