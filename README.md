# my-hackintosh

## OpenCore and kexts

1. https://github.com/acidanthera/OpenCorePkg
2. https://github.com/acidanthera/VirtualSMC/releases
3. https://github.com/acidanthera/Lilu/releases
4. https://github.com/acidanthera/WhateverGreen/releases
5. https://github.com/acidanthera/AppleALC/releases
6. https://github.com/acidanthera/NVMeFix/releases
7. https://github.com/OpenIntelWireless/itlwm/releases
8. https://github.com/OpenIntelWireless/IntelBluetoothFirmware/releases

## BIOS settings

### Advanced

#### CPU Configuration

| Option                                | Value                                |
| ------------------------------------- | ------------------------------------ |
| Software Guard Extensions (SGX)       | Disabled                             |
| Intel (VMX) Virtualization Technology | Enabled                              |
| Hyper-Threading                       | Enabled                              |

#### System Agent (SA) Configuration

| Option        | Value                                |
| ------------- | ------------------------------------ |
| VT-d          | Enabled                              |

#### PCH Storage Configuration

| Option              | Value                                |
| ------------------- | ------------------------------------ |
| SATA Mode Selection | AHCI                                 |

#### Thunderbolt(TM) Configuration

| Option                           | Value                                |
| -------------------------------- | ------------------------------------ |
| Discrete Thunderbolt(TM) Support | Enabled (Disabled for installation)  |

#### PCI Subsystem Settings

| Option              | Value                                |
| ------------------- | ------------------------------------ |
| Above 4G Decoding   | Enabled                              |
| Re-Size BAR Support | Disabled                             |

#### USB Configuration

| Option              | Value                                |
| ------------------- | ------------------------------------ |
| XHCI Hand-off       | Enabled                              |

### Boot

#### CSM (Compatibility Support Module)

| Option        | Value                                |
| ------------- | ------------------------------------ |
| Launch CSM    | Disabled                             |

#### Boot Configuration

| Option        | Value                                |
| ------------- | ------------------------------------ |
| Fast Boot     | Disabled                             |

## SMBIOS

| Name          | Value                                |
| ------------- | ------------------------------------ |
| System Model  | iMac20,2                             |
| Serial Number | C02DL0MD046M                         |
| MLB           | C02043300GU0000UE                    |
| SmUUID        | 276D5B6E-6894-4CF0-ADFC-FC7384387173 |
| ROM           | f0:18:98:3e:34:28                    |

## Hardware

| Category     | Model                                         | Code                          | Official Link             |
| ------------ | --------------------------------------------- | ----------------------------- | ------------------------- |
| Motherboard  | ASUS ROG Maximus XII Formula                  |                               | https://rog.asus.com/motherboards/rog-maximus/rog-maximus-xii-formula-model/ |
|   Chipset    | Intel® Z490                                   |                               | https://ark.intel.com/content/www/us/en/ark/products/201834/intel-z490-chipset.html |
| CPU          | Intel® Core™ i9-10900K Processor              | Comet Lake                    | https://ark.intel.com/content/www/us/en/ark/products/199332/intel-core-i9-10900k-processor-20m-cache-up-to-5-30-ghz.html |
| CPU Cooler   | ASUS Rog Ryujin 360                           |                               | https://rog.asus.com/cooling/cpu-liquid-coolers/rog-ryujin/rog-ryujin-360-model/ |
| Memory       | HyperX Fury Black 64GB 3600MHz DDR4 CL18 DIMM | HX436C18FB3K2/64              | https://www.hyperxgaming.com/us/memory/fury-ddr4 |
| Video Card   | ASUS ROG Strix Radeon RX 5500 XT              | ROG-STRIX-RX5500XT-O8G-GAMING | https://rog.asus.com/hk-en/graphics-cards/graphics-cards/rog-strix/rog-strix-rx5500xt-o8g-gaming-model/ |
| Keyboard     | Logitech Craft                                |                               | https://www.logitech.com/en-us/products/keyboards/craft.920-008484.html |
| Mouse        | Logitech MX Master 3                          |                               | https://www.logitech.com/en-us/products/mice/mx-master-3.910-005620.html

## CPU Model

```bash
cat /proc/cpuinfo | grep 'model name'
```

```
model name	: Intel(R) Core(TM) i9-10900K CPU @ 3.70GHz
```

## GPU Model

```bash
lspci | grep -i --color 'vga\|3d\|2d'
```

```
03:00.0 VGA compatible controller: Advanced Micro Devices, Inc. [AMD/ATI] Navi 14 [Radeon RX 5500/5500M / Pro 5500M] (rev c5)
```

## Chipset Model

```bash
dmidecode -t baseboard
```

```
# dmidecode 3.2
Getting SMBIOS data from sysfs.
SMBIOS 3.2.0 present.

Handle 0x0002, DMI type 2, 15 bytes
Base Board Information
	Manufacturer: ASUSTeK COMPUTER INC.
	Product Name: ROG MAXIMUS XII FORMULA
	Version: Rev 1.xx
	Serial Number: 200873144700122
	Asset Tag: Default string
	Features:
		Board is a hosting board
		Board is replaceable
	Location In Chassis: Default string
	Chassis Handle: 0x0003
	Type: Motherboard
	Contained Object Handles: 0

Handle 0x0034, DMI type 10, 6 bytes
On Board Device Information
	Type: Video
	Status: Enabled
	Description:    To Be Filled By O.E.M.

Handle 0x0060, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard - Other
	Type: Other
	Status: Enabled
	Type Instance: 1
	Bus Address: 0000:00:00.0

Handle 0x0061, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard - Other
	Type: Other
	Status: Enabled
	Type Instance: 2
	Bus Address: 0000:00:14.0

Handle 0x0062, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard - Other
	Type: Other
	Status: Enabled
	Type Instance: 3
	Bus Address: 0000:00:14.2

Handle 0x0063, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard - Ethernet
	Type: Ethernet
	Status: Enabled
	Type Instance: 1
	Bus Address: 0000:00:14.3

Handle 0x0064, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard - Other
	Type: Other
	Status: Enabled
	Type Instance: 4
	Bus Address: 0000:00:15.0

Handle 0x0065, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard - Other
	Type: Other
	Status: Enabled
	Type Instance: 5
	Bus Address: 0000:00:15.1

Handle 0x0066, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard - Other
	Type: Other
	Status: Enabled
	Type Instance: 6
	Bus Address: 0000:00:16.0

Handle 0x0067, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard - SATA
	Type: SATA Controller
	Status: Enabled
	Type Instance: 1
	Bus Address: 0000:00:17.0

Handle 0x0068, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard - Other
	Type: Other
	Status: Enabled
	Type Instance: 7
	Bus Address: 0000:00:1f.0

Handle 0x0069, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard - Sound
	Type: Sound
	Status: Enabled
	Type Instance: 1
	Bus Address: 0000:00:1f.3

Handle 0x006A, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard - Other
	Type: Other
	Status: Enabled
	Type Instance: 8
	Bus Address: 0000:00:1f.4

Handle 0x006B, DMI type 41, 11 bytes
Onboard Device
	Reference Designation: Onboard - Other
	Type: Other
	Status: Enabled
	Type Instance: 9
	Bus Address: 0000:00:1f.5
```

## Keyboard, Trackpad and Touchscreen Connection Type

```bash
dmesg |grep -i 'input'
```

```
[    0.525429] input: Sleep Button as /devices/LNXSYSTM:00/LNXSYBUS:00/PNP0C0E:00/input/input0
[    0.525456] input: Power Button as /devices/LNXSYSTM:00/LNXSYBUS:00/PNP0C0C:00/input/input1
[    0.525477] input: Power Button as /devices/LNXSYSTM:00/LNXPWRBN:00/input/input2
[    3.265996] hid-generic 0003:0B05:18F3.0001: hiddev0,hidraw0: USB HID v1.11 Device [AsusTek Computer Inc. AURA LED Controller] on usb-0000:00:14.0-11/input2
[    3.266069] input: Logitech USB Receiver as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.1/1-2.1:1.0/0003:046D:C52B.0002/input/input3
[    3.323786] hid-generic 0003:046D:C52B.0002: input,hidraw1: USB HID v1.11 Keyboard [Logitech USB Receiver] on usb-0000:00:14.0-2.1/input0
[    3.324387] input: Logitech USB Receiver Mouse as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.1/1-2.1:1.1/0003:046D:C52B.0003/input/input4
[    3.324883] input: Logitech USB Receiver Consumer Control as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.1/1-2.1:1.1/0003:046D:C52B.0003/input/input5
[    3.383711] input: Logitech USB Receiver System Control as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.1/1-2.1:1.1/0003:046D:C52B.0003/input/input6
[    3.384162] hid-generic 0003:046D:C52B.0003: input,hiddev1,hidraw2: USB HID v1.11 Mouse [Logitech USB Receiver] on usb-0000:00:14.0-2.1/input1
[    3.384674] hid-generic 0003:046D:C52B.0004: hiddev2,hidraw3: USB HID v1.11 Device [Logitech USB Receiver] on usb-0000:00:14.0-2.1/input2
[    3.385037] hid-generic 0003:0B05:1936.0005: hiddev3,hidraw4: USB HID v1.11 Device [AsusTek Computer Inc. AURA LED Controller] on usb-0000:00:14.0-12/input0
[    3.385393] input: Logitech USB Receiver as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.2/1-2.2:1.0/0003:046D:C52B.0006/input/input8
[    3.436451] hid-generic 0003:0B05:18AE.0009: hiddev4,hidraw5: USB HID v1.11 Device [AsusTek Computer Inc. ROG_RYUJIN] on usb-0000:00:14.0-13.2/input0
[    3.443837] hid-generic 0003:046D:C52B.0006: input,hidraw6: USB HID v1.11 Keyboard [Logitech USB Receiver] on usb-0000:00:14.0-2.2/input0
[    3.444495] input: Logitech USB Receiver Mouse as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.2/1-2.2:1.1/0003:046D:C52B.0007/input/input9
[    3.445032] input: Logitech USB Receiver Consumer Control as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.2/1-2.2:1.1/0003:046D:C52B.0007/input/input10
[    3.503713] input: Logitech USB Receiver System Control as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.2/1-2.2:1.1/0003:046D:C52B.0007/input/input11
[    3.504153] hid-generic 0003:046D:C52B.0007: input,hiddev5,hidraw7: USB HID v1.11 Mouse [Logitech USB Receiver] on usb-0000:00:14.0-2.2/input1
[    3.504671] hid-generic 0003:046D:C52B.0008: hiddev6,hidraw8: USB HID v1.11 Device [Logitech USB Receiver] on usb-0000:00:14.0-2.2/input2
[    3.665309] logitech-djreceiver 0003:046D:C52B.0004: hiddev1,hidraw1: USB HID v1.11 Device [Logitech USB Receiver] on usb-0000:00:14.0-2.1/input2
[    3.785686] input: Logitech Wireless Device PID:4066 Keyboard as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.1/1-2.1:1.2/0003:046D:C52B.0004/0003:046D:4066.000A/input/input13
[    3.831807] input: Logitech Wireless Device PID:4066 Mouse as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.1/1-2.1:1.2/0003:046D:C52B.0004/0003:046D:4066.000A/input/input14
[    3.832304] input: Logitech Wireless Device PID:4066 Consumer Control as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.1/1-2.1:1.2/0003:046D:C52B.0004/0003:046D:4066.000A/input/input15
[    3.863775] input: Logitech Wireless Device PID:4066 System Control as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.1/1-2.1:1.2/0003:046D:C52B.0004/0003:046D:4066.000A/input/input16
[    3.895889] hid-generic 0003:046D:4066.000A: input,hidraw2: USB HID v1.11 Keyboard [Logitech Wireless Device PID:4066] on usb-0000:00:14.0-2.1/input2:1
[    3.929289] logitech-djreceiver 0003:046D:C52B.0008: hiddev2,hidraw3: USB HID v1.11 Device [Logitech USB Receiver] on usb-0000:00:14.0-2.2/input2
[    4.050066] input: Logitech Wireless Device PID:4082 Keyboard as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.2/1-2.2:1.2/0003:046D:C52B.0008/0003:046D:4082.000B/input/input20
[    4.051312] input: Logitech Wireless Device PID:4082 Mouse as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.2/1-2.2:1.2/0003:046D:C52B.0008/0003:046D:4082.000B/input/input21
[    4.052539] hid-generic 0003:046D:4082.000B: input,hidraw6: USB HID v1.11 Keyboard [Logitech Wireless Device PID:4082] on usb-0000:00:14.0-2.2/input2:1
[    4.227183] input: Logitech Craft as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.1/1-2.1:1.2/0003:046D:C52B.0004/0003:046D:4066.000A/input/input25
[    4.227502] logitech-hidpp-device 0003:046D:4066.000A: input,hidraw2: USB HID v1.11 Keyboard [Logitech Craft] on usb-0000:00:14.0-2.1/input2:1
[    4.325144] input: Logitech MX Master 3 as /devices/pci0000:00/0000:00:14.0/usb1/1-2/1-2.2/1-2.2:1.2/0003:046D:C52B.0008/0003:046D:4082.000B/input/input26
[    4.325412] logitech-hidpp-device 0003:046D:4082.000B: input,hidraw6: USB HID v1.11 Keyboard [Logitech MX Master 3] on usb-0000:00:14.0-2.2/input2:1
[    5.141861] input: Eee PC WMI hotkeys as /devices/platform/eeepc-wmi/input/input27
[    5.212777] input: HDA ATI HDMI HDMI/DP,pcm=3 as /devices/pci0000:00/0000:00:01.0/0000:01:00.0/0000:02:00.0/0000:03:00.1/sound/card1/input28
[    5.212807] input: HDA ATI HDMI HDMI/DP,pcm=7 as /devices/pci0000:00/0000:00:01.0/0000:01:00.0/0000:02:00.0/0000:03:00.1/sound/card1/input29
[    5.212830] input: HDA ATI HDMI HDMI/DP,pcm=8 as /devices/pci0000:00/0000:00:01.0/0000:01:00.0/0000:02:00.0/0000:03:00.1/sound/card1/input30
[    5.212857] input: HDA ATI HDMI HDMI/DP,pcm=9 as /devices/pci0000:00/0000:00:01.0/0000:01:00.0/0000:02:00.0/0000:03:00.1/sound/card1/input31
[    5.212881] input: HDA ATI HDMI HDMI/DP,pcm=10 as /devices/pci0000:00/0000:00:01.0/0000:01:00.0/0000:02:00.0/0000:03:00.1/sound/card1/input32
[    5.228631] snd_hda_codec_realtek hdaudioC0D0:    inputs:
[    5.255758] input: HDA Intel PCH Front Mic as /devices/pci0000:00/0000:00:1f.3/sound/card0/input33
[    5.255784] input: HDA Intel PCH Rear Mic as /devices/pci0000:00/0000:00:1f.3/sound/card0/input34
[    5.255803] input: HDA Intel PCH Line as /devices/pci0000:00/0000:00:1f.3/sound/card0/input35
[    5.255829] input: HDA Intel PCH Line Out Front as /devices/pci0000:00/0000:00:1f.3/sound/card0/input36
[    5.255847] input: HDA Intel PCH Line Out Surround as /devices/pci0000:00/0000:00:1f.3/sound/card0/input37
[    5.255879] input: HDA Intel PCH Line Out CLFE as /devices/pci0000:00/0000:00:1f.3/sound/card0/input38
[    5.255906] input: HDA Intel PCH Front Headphone as /devices/pci0000:00/0000:00:1f.3/sound/card0/input39
[   20.455602] rfkill: input handler disabled
```

## Audio Codec

```bash
aplay -l
```

```
**** List of PLAYBACK Hardware Devices ****
card 0: PCH [HDA Intel PCH], device 0: ALC1220 Analog [ALC1220 Analog]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 0: PCH [HDA Intel PCH], device 1: ALC1220 Digital [ALC1220 Digital]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: HDMI [HDA ATI HDMI], device 3: HDMI 0 [HDMI 0]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: HDMI [HDA ATI HDMI], device 7: HDMI 1 [HDMI 1]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: HDMI [HDA ATI HDMI], device 8: HDMI 2 [HDMI 2]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: HDMI [HDA ATI HDMI], device 9: HDMI 3 [HDMI 3]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: HDMI [HDA ATI HDMI], device 10: HDMI 4 [HDMI 4]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
```

## Network Controller models

Basic info:

```bash
lspci | grep -i 'network'
```

```
00:14.3 Network controller: Intel Corporation Wi-Fi 6 AX201
```

More in-depth info:

```bash
lshw -class network
```

```
  *-network                 
       description: Wireless interface
       product: Wi-Fi 6 AX201
       vendor: Intel Corporation
       physical id: 14.3
       bus info: pci@0000:00:14.3
       logical name: wlo1
       version: 00
       serial: 34:2e:b7:19:e0:56
       width: 64 bits
       clock: 33MHz
       capabilities: pm msi pciexpress msix bus_master cap_list ethernet physical wireless
       configuration: broadcast=yes driver=iwlwifi driverversion=5.8.0-44-generic firmware=55.d9698065.0 QuZ-a0-hr-b0-55.u ip=192.168.1.10 latency=0 link=yes multicast=yes wireless=IEEE 802.11
       resources: iomemory:400-3ff irq:16 memory:4010314000-4010317fff
  *-network
       description: Ethernet interface
       product: AQC107 NBase-T/IEEE 802.3bz Ethernet Controller [AQtion]
       vendor: Aquantia Corp.
       physical id: 0
       bus info: pci@0000:06:00.0
       logical name: enp6s0
       version: 02
       serial: 3c:7c:3f:2b:94:86
       capacity: 10Gbit/s
       width: 64 bits
       clock: 33MHz
       capabilities: pciexpress pm msix msi vpd bus_master cap_list rom ethernet physical tp 100bt-fd 1000bt-fd 10000bt-fd autonegotiation
       configuration: autonegotiation=on broadcast=yes driver=atlantic driverversion=5.8.0-44-generic duplex=full firmware=3.1.71 latency=0 link=no multicast=yes port=twisted pair
       resources: irq:16 memory:90440000-9044ffff memory:90450000-90450fff memory:90000000-903fffff memory:90400000-9043ffff
  *-network
       description: Ethernet interface
       product: Intel Corporation
       vendor: Intel Corporation
       physical id: 0
       bus info: pci@0000:07:00.0
       logical name: enp7s0
       version: 02
       serial: 3c:7c:3f:2b:94:85
       capacity: 1Gbit/s
       width: 32 bits
       clock: 33MHz
       capabilities: pm msi msix pciexpress bus_master cap_list ethernet physical 10bt 10bt-fd 100bt 100bt-fd 1000bt-fd autonegotiation
       configuration: autonegotiation=on broadcast=yes driver=igc driverversion=0.0.1-k latency=0 link=no multicast=yes port=twisted pair
       resources: irq:18 memory:90500000-905fffff memory:90600000-90603fff
  *-network
       description: Ethernet interface
       physical id: 2
       logical name: veth6794ea9
       serial: 86:b4:c5:3d:c9:ac
       size: 10Gbit/s
       capabilities: ethernet physical
       configuration: autonegotiation=off broadcast=yes driver=veth driverversion=1.0 duplex=full link=yes multicast=yes port=twisted pair speed=10Gbit/s
```

## Drive Model

```bash
lshw -class disk -class storage
```

```
  *-sata                    
       description: SATA controller
       product: Intel Corporation
       vendor: Intel Corporation
       physical id: 17
       bus info: pci@0000:00:17.0
       version: 00
       width: 32 bits
       clock: 66MHz
       capabilities: sata msi pm ahci_1.0 bus_master cap_list
       configuration: driver=ahci latency=0
       resources: irq:129 memory:90a00000-90a01fff memory:90a03000-90a030ff ioport:4050(size=8) ioport:4040(size=4) ioport:4020(size=32) memory:90a02000-90a027ff
  *-scsi:0
       physical id: 9
       logical name: scsi0
       capabilities: emulated
     *-disk
          description: ATA Disk
          product: Samsung SSD 850
          physical id: 0.0.0
          bus info: scsi@0:0.0.0
          logical name: /dev/sda
          version: 2B6Q
          serial: S252NXAGA15841N
          size: 953GiB (1024GB)
          capabilities: gpt-1.00 partitioned partitioned:gpt
          configuration: ansiversion=5 guid=fbae2975-cc73-41bf-acbb-d49f5a0c8c4a logicalsectorsize=512 sectorsize=512
  *-scsi:1
       physical id: a
       logical name: scsi1
       capabilities: emulated
     *-disk
          description: ATA Disk
          product: SanDisk SDSSDX24
          physical id: 0.0.0
          bus info: scsi@1:0.0.0
          logical name: /dev/sdb
          version: R201
          serial: 124888404405
          size: 223GiB (240GB)
          capabilities: gpt-1.00 partitioned partitioned:gpt
          configuration: ansiversion=5 guid=5fbdba98-dc69-4bb5-85b8-dc2748e25669 logicalsectorsize=512 sectorsize=512
```
