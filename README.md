# Asmedia-AS2105-sata-to-USB-3
FW Upgrade procedure

Story:
There are many different Brands of sata to USB 3.0 external enclosures.
but most have same plastic and same PCB with same IC controller...

I have Thermaltake  BlackX 5G
P/N ST0019
single drive.
i had the dual sata drive bay version, but returned because,
in those days i only had 3.5", there were No ssd,
and large 2.5" were rare.
problem is that 2TB 3.5" drives Eat 12v 5A at Spin-Up / Start-Up.
if you see the AC-DC power adapter included is only 2A.
2 drives to start-up at same time is 10A,

1x drive bay works replacing the AC-DC adapter from Transformer to Switch mode 3A,
Drives will Clip, but will start-up.

Anyway...
There are other brands with same plastic case,
and most with same Asmedia AS2105 controller IC.

Problem #2. is that New Drives, Big Drives, like Seagate Exos 18TB ST18000NM013J
were Not available when the Firmware of the AS2105 was made...
will Not work, unless you Upgrade the Firmware of the AS2105, and Configuration Flags.

as you can guess, the Firmware is Not available from Official Asmedia website, only investors .pdf
and information about New IC.

but you can find most Firmwares here:
https://www.usbdev.ru/files/asmedia/asmt2105firmware/

i used:
Firmware ASMT-2105 [130423_11_AC_04.bin] ; 130423_11_AC_04.rar
https://www.usbdev.ru/?wpfb_dl=9235

also you need the Asmedia MP Tool v3.6.3.0
https://www.usbdev.ru/files/asmedia/asm105mptool/

but i used other, 
https://www.station-drivers.com/index.php/en/driverss/Drivers/Asmedia/ASM-105x-115x-215x-(ASMT-xxxx)-Sata-USB-3.x-controllers/Utilitaires-(Utilities)/lang,en-gb/

21.20.1 has a Unknown Password "Does Not allow to Burn the New Firmware"
but has a nice Firmware Stand Alone FW Version Reasder.
https://www.station-drivers.com/index.php/en/driverss/Drivers/Asmedia/ASM-105x-115x-215x-(ASMT-xxxx)-Sata-USB-3.x-controllers/Utilitaires-(Utilities)/Asmedia-ASM-21xx-MPTools-Version-2.1.20.1/lang,en-gb/

21.21.5
works No password, but does Not have the stand alone FW Reader tool.
https://www.station-drivers.com/index.php/en/driverss/Drivers/Asmedia/ASM-105x-115x-215x-(ASMT-xxxx)-Sata-USB-3.x-controllers/Utilitaires-(Utilities)/Asmedia-ASM-21xx-MPTools-Version-2.1.21.5/lang,en-gb/

One Touch Back-up is Optional Download:
https://www.station-drivers.com/index.php/en/driverss/Drivers/Asmedia/ASM-105x-115x-215x-(ASMT-xxxx)-Sata-USB-3.x-controllers/Utilitaires-(Utilities)/Asmedia-One-Touch-Backup-Version-1.4.1.0/lang,en-gb/



The Way to Upgrade the FW is very simple, 
just Turn-On the External USB enclosure, WITHOUT a Drive "Empty",
Then Open the MP Tool software,
Manually Write the Brand, Model, Serial Number "must be 12 numbers" 
i have 2 External Enclosures, my new serials are 000000000001 and 000000000002
but does Not matter, factory serials were: 0000000000000000000000000
No Brasnd, No Model.
No configuration Flags.

Worked "by miracle".

IDLE Time NONE.

Config Flags:
Everything exept: Custom Code "The 1st setting", and 2TB.
QD32 im undecided...
i have it [X] Active, but... MP Tool software always default to [ ] Deactivated.
There is Not much info about QD32.

IF you select 2TB [X] Active,
will split & limit large HDD over 2TB, force create a 2TB partition = BAD.
that option does Not affect 2TB or smaller drives.

http://hdtune.com/
Free 2.55 version did Not detected the large drive,
Paid v5 worked,
But only after Updating the AS2105 Firmware.
and only after Activating,

if you try to run Non Activated, with Old FW will paralize.
Not even End Task will work.

Thats it.
i also have a PCIe USB3.0 card, updated FW,
USB3.0 speed depends on the PCIe lanes availables on the Board.
if you have more PCIe cards, will eat PCIe lanes.
if you place the PCIe card in a Limited slot, also.

To be honset purchasing a Large Mechanical Drive is risky.
too delicated.
i hope someday 8TB SSD or M.2 QLC becomes cheaper, price difference is too much.

-----
Optional:
Unofficial FW Reader Dumper
MP Tools Reads but do Not extract Firmwate stored in the IC.

https://github.com/smx-smx/ASMTool
