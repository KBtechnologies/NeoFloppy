#   NeoFloppy
###  Specification
####  Version 0.1.3a
###### NOTE: This is a "work in progress" draft and NOT a final specification!
###### Fundamental things may be changed without prior notice!
This specification is open for development and request for comment.

#### Comments and Suggestions are recommended to be submitted as issues.


## Goal
The NeoFloppy aims to be a modern removeable media format & standard taking lessions learned from the 1st 3,5" FDD up to present-day SSDs & [NV-]RAM media and developing an easy to handle and use media format.

It is intended to be an open standard that is both mutli-vendor & multi-provider, allowing for an equally diverse ecosystem as the original 3,5" FDD in the mid-90s.


###  Why another media type?
Why is an important question and we want to answer it:

####  Longevity
All common external media either suffer from certain issues:
- being extremely delicate on their own [i.e. blu-ray disks]
- having a very limited numer of connection cycles as per interface [i.e. 2,5" SSDs]
- being a mechanical hazard being being able to break off their connectors and/or destroying the ports connected to if not damage the entire machine the port belongs to [i.e. USB flashdrives].
- Conventional Harddrives are mechanically fragile and susceptible to damages due to user error, "gravity" magnetic fields, etc.
  - It is evident that the [over 65 years old technology of HDDs](https://en.wikipedia.org/wiki/Hard_disk_drive) cannot long-term compete in terms of capacity growth and storage pricing with SSDs as already the technological limits are being reached using all tricks in the book like [SMR](https://en.wikipedia.org/wiki/Shingled_magnetic_recording) and using [Helium](https://en.wikipedia.org/wiki/Helium#Conservation_advocates) for cooling, which is a very finite resource.
  - Hard drives already are way too power consuming for more and more applications and thus will likely go the way of [QIC Tapes](https://en.wikipedia.org/wiki/Quarter-inch_cartridge) as their shortcomings make them more and more unjustifyable for mass-market use by [SOHO](https://en.wikipedia.org/wiki/Small_office/home_office) customer.
  - External Hard-Drive Systems always suffer from scalability issues, quickly killing any monetary advantage and making media and drives horribly obsolete, as many companies and products have shown:
    - All of [SyQuest](https://en.wikipedia.org/wiki/SyQuest_Technology)'s products [which failed due to lack of roadmap and innovation](https://www.youtube.com/watch?v=211-eHVkqeo).
    - [Castlewood Orb Drive](https://en.wikipedia.org/wiki/Castlewood_Orb_Drive)
    - [iomega Jaz](https://en.wikipedia.org/wiki/Jaz_drive) & [iomega Rev](https://en.wikipedia.org/wiki/REV_(disk))
    - [RDX](https://en.wikipedia.org/wiki/RDX_Technology) (which are basically just overpriced HDDs & SSDs inside a fancy cartridge) 

####  Handling
All common external media have serious handing deficits stemming from lack of standardization.
- USB flashdrives - as small and handy as they are - lack any good way to label them.
  - This often enough results in users fumbling around with drives, espechally when they have a large quantity of equally-looking ones. 
    - Flashdrives never were "designed" with handeability, accessibility or useability in mind. So essential Quality-of-Life features common on other media from 8" FDDs to BD-RWs like labelling or even a good way to store them efficiently was never the focus for them.
- With the notable exception of [LTO Ultrium](https://en.wikipedia.org/wiki/Linear_Tape-Open#Mechanisms) most modern media do not account for automated "Media Libraries" including [Autoloaders](https://en.wikipedia.org/wiki/Tape_library#Autoloaders) and the need to store and archive a bigger quantity of media and automatically retrieve them.

The [3,5" FDD did these things quite well](https://youtu.be/tJCMzdzh4Tw?t=95), but the used technology is hopelessly outdated in [the age of legitimate 1 TB microSD cards](https://www.ign.com/articles/the-best-1tb-microsd-cards).


###  Why the 3,5" FDD form factor?
OFC it would be trivial to find even smaller form factors like [EDSFF](https://en.wikipedia.org/wiki/Enterprise_%26_Data_Center_SSD_Form_Factor), [M.2](https://en.wikipedia.org/wiki/M.2) & [ExpressCard/34](https://en.wikipedia.org/wiki/ExpressCard) but certain key points come to mind:
- Some smaller form factors may be subject to licensing fees and not be an open standard.
  - This is the case with basically almost all media on the market as of today that ain't so old that any patents have long lapsed.
    - The 3,5" FDD form factor certainly is one of those legacy formats.
- The form factor has several key advantages as stated before, and aside from [Fuzzy Warm Retro Feelings](https://www.youtube.com/watch?v=8IZcP0oP0OU), conversions of 3,5" media and drives using [SD Cards](https://en.wikipedia.org/wiki/SD_card) are [common](https://www.youtube.com/watch?v=gNQYbSWBhAs) and [well-documented](https://www.youtube.com/watch?v=GOdIeka3-SI).
  - Sadly these are usually [hand-fitted](https://www.youtube.com/watch?v=END_PVp3Eds) and not interchangeable in any way or form.
  - Also The SD Interface doesn't lend itself for use-cases replacing SSDs so [SD Express](https://en.wikipedia.org/wiki/SD_card#SD_Express) basically implements [NVMe](https://en.wikipedia.org/wiki/NVM_Express) and thus [PCIe](https://en.wikipedia.org/wiki/PCI_Express).
    - Native PCIe support might be more useful.
- Modern, high-speed & high density flash media can become [very toasty](https://www.youtube.com/watch?v=lQmI5A27Iv8), resulting in a lower lifespan.
  - The 3,5" form factor provides ample of surface area to allow for sufficient passive cooling [like metal-encased 2,5" SSDs] whilst not contributing to excessive device "thiccness".
- Existing tooling, standards and a known form factor make tooling up for such a media format relatively easy.
  - Even additional casings like a [Jewelcase](https://memorypack.com.tw/floppy-disk.html) providing a [convenient transport and long-term storeability](https://www.youtube.com/watch?v=J1MN6O4dCCw) are commercially existing. 
- Not only does the form factor of the [iomega Zip Disk](https://en.wikipedia.org/wiki/Zip_drive) lack many of these cost-saving advantages - mostly due to their single-vendor approach to drives, but also lack of benefits beyond "thiccer casing".

In short, the 3,5" form factor has a lot of desireable features for a removeable media, like being pretty much ["idiot-proof"](https://youtu.be/tJCMzdzh4Tw?t=149), acknowledging the [shortcomings of 5,25" FDDs](https://youtu.be/tJCMzdzh4Tw?t=228) and impoving upon them.

The [core advantages of the 3,5" FDDs](https://youtu.be/tJCMzdzh4Tw?t=254) are therefore taken and remixed into a new and better media format.


## Media Types
The following Types of NeoFloppy are specified:
- [WORM](https://en.wikipedia.org/wiki/Write_once_read_many)
  - Specifically for append-only archival media.
    - No, you don't need blockchain for that!
- [ROM](https://en.wikipedia.org/wiki/Read-only_memory)
  - Which may be interesting not only for commercially sold media and applications, but also for persistent and secure embedded systems designed to be airgapped.
    - I.e. industrial automation and critical infrastructure.
- [RAM](https://en.wikipedia.org/wiki/RAM_drive#Dedicated_hardware_RAM_drives) / Voltaile Memory
  - These may be useful for fast IOPS storage [i.e. scratchdisks] where the longevity is more important than the price per capacity.
    - I.e. Video recording and Movie editing applications.
  - RAM media must have a transparent refresh circuitry and toolfree swappable & rechargeable batteries/capacitors configured for redundancy.
  - They should also employ ECC and explicitly designate if they don't do so.
- Re-Writeable
  - These may be SSD and/or NVRAM-based and will combine the advantages of USB flashdrives, 2,5" SSDs and 3,5" FDDs without any disadvantages.
- Cleaning Media
  - These don't contain any electrical contacts but are designed to clean the heads of drives.
  - A subsequent "cleaning drive" to clean media is also planned, tho unless physical damage has been exerted onto the media, it should be easily cleanable with 99% isopropylic alcohol and a non-static & fine-tipped sponge-swab.
    - Rare cases of severly gunked-up disks and/or drives will be cleaned by [Kontakt Chemie LR PCC](http://www.kontaktchemie.com/KOC/KOCproductdetailV2.csp?product=KONTAKT%20PCC) or similar Printed Circuit Board Cleaner if not ultrasonic cleaning.
  - The need for any cleaning should be negligible [1x each 5-10 years] per drives and non-zero for media given they get handled properly as per manufacturer specification.

##  Mechanical Dimensions
###    Media
Unless specified otherwise, the media should follow the [ECMA-125](https://www.ecma-international.org/wp-content/uploads/ECMA-125_1st_edition_december_1987.pdf) dimension standards.
####   Casing
Overall:    93,7 x 90,0 x 3,3 mm.
- Identical with 3,5" FDDs
  - Spindle in the middle is not existing - instead it's bottom side is flat and used to place the back label on
  - Holes identical to 2.880kB FDD
    - Including Write-protect hole/switch
      - Write protect must be respected by the drive AND also be enforced by the media
      - Write Protect switch must be electrically integrated into the controller of the media.

Note: The casing is recommended to be made from Aluminium alloy of 0,5mm strenght per side.
Mechanically strong alloys like [Al7050](https://en.wikipedia.org/wiki/7050_aluminium_alloy), [Al7055-T6](https://en.wikipedia.org/wiki/7055_aluminium_alloy), [Al6061-T651](https://en.wikipedia.org/wiki/6061_aluminum_alloy), [Al6063-T6](https://en.wikipedia.org/wiki/6063_aluminium_alloy), [Al5059-H321](https://en.wikipedia.org/wiki/5059_aluminium_alloy) is encouraged, but the use of [Al4043](https://en.wikipedia.org/wiki/4043_aluminium_alloy) or even [Al1050](https://en.wikipedia.org/wiki/1050_aluminium_alloy) isn't banned per-se.

However it is recommended to use Al4043 & Al1050 primarily as "filler" to affix the PCB internally within the case.

Other materials, including polymers [with or without fiber support] are allowed if these do not posess worse properties in terms of mechanical strenght and longevity of media.

The use of magnetic, magnetized or magentizeable case materials is not allowed!

The media is designed to be of 3,3mm total thickness.
This is divided up by the following parameters:
-   2x 0,5mm = 1mm metal Casing.
    - 0,5mm on top and 0,5mm on bottom
- 2x 0,05mm = 0,1mm labels 
  - it is recommended to use one consistent "over the corner" label!
    - This allows for easy integration of the "rear label" which is the 1D-Barcode with the unique serial number and manufacturer prefix.
      - Similar to [LTO Ultrium](https://en.wikipedia.org/wiki/Linear_Tape-Open#Labels), [Sony AIT](https://en.wikipedia.org/wiki/Advanced_Intelligent_Tape) and [IBM 3592](https://en.wikipedia.org/wiki/IBM_3592) tape cartridges.
      - An Example can be found [here](docs/images/128bit_code128-example.gif)
  - Top label: includes rewriteable NFC Tag [13,56 MHz - i.e. using NTAG215]
    - Designed for media identification
      - Can be re-labeled within the drive [optional]
        - Name of the media
  - Bottom label: includes read-only RFID Tag [125kHz - i.e. using EM4100]
    - Designed for Media Type Identification
      - Labeled at factory!
        - Manufacturer
        - Product Name and Series, including SKU for drop-in replacements
          - Unique Media Serial Number
          - Date of Production
          - Also printed onto the label as QR code for automated optical identification. 
      - Distinguishes the following types:
        - Writeability of the medium
          - [WORM](https://en.wikipedia.org/wiki/Write_once_read_many)
          - Re-Writeable
          - RAM / Voltaile Memory
          - [ROM](https://en.wikipedia.org/wiki/Read-only_memory)
        - Media Type
          - Archival / WORM
          - Flash
            - [Type & Organization] i.e. QLC eMMC 
          - RAM
            - [Type & Organization] i.e. 128GB [1TBit] DDR5-3200-ECC [8x 128GBit]
          - ROM
            - Including Type and Title
        - Rated Lifecycle
          - Shelf-Life
          - Data Retention
          - Full-Disk Write Cycles
          - Total Data Written
          - This also must be a legally enforceable guarantee to the point that underperforming [less than 95% rated] is subject to free media replacements. 
  - Rated Capacity
    - [in x * y ^z TiB]
      - This capacity MUST be guaranteed to be available 100% after formatting. (Similar to SAS HDDs & SSDs)
      - Media Manufacturers are solely responsible to provide sufficient capacity and reserves to fullfill this criteria for the entire media lifespan.
      - On ROM media, this will state the capacity of the used filesystem.
  - Rated Speeds [read/write]
    - [in Mebibyte/s]
      - This speed must be guaranteed to be available for the entire rated capacity. (Similar to [Video Speed Class](https://en.wikipedia.org/wiki/SD_card#Video_Speed_Class) on SD Cards).
      - It must be indicated on the media in case the write and read speeds differ.
        - i.e. "w128 / r256" if the media can be written to at 128 MiByte/s but read at 1024 MiByte/s.
        - Otherwise, the media must have equal read & write speeds guaranteed, and only designate their write speeds [i.e. w128].
        - ROM media will instead designate their read speeds [i.e. r256].
- 2,2 mm internal space
  - 0,8 mm [+/- 10%] PCB thickness [total, at contact window. Internal thickness can be even thinner]
    - Thinner PCBs at contact are allowed if they are adequately supported and - if necessary - raised to be within 0,05mm height tolerance.
      - This is due to the use of [LGA](https://en.wikipedia.org/wiki/Land_grid_array) contacting on the medium.
        - The "Drive Head" is basically a "LGA socket" that electromechanically contacts the media within the "contact window" which is protected by the mechanical shutter.
  - 1,2mm - 1,35mm [if PCB thickness is 0,8 mm] component thickness
    - This ie equal to [S1 / S2 Type M.2 SSDs](https://en.wikipedia.org/wiki/M.2#Form_factors_and_keying).
    - double-sided media are also valid, as long as they fit within the confines of the 2,2mm internal media thickness.
  - 0,2 - 0,05mm "Thermal Interface Material" (TIM) aka. [Thermal Paste](https://en.wikipedia.org/wiki/Thermal_paste)
    - If PCB thickness is 0,8mm and Component Thickness is 1,2-1,35mm.
    - The use of  TIM with appropriate quality is encouraged to increase media longevity and aid with cooling under high stress.


####   PCB
Aside from the contact window area and subsequent pinouts, the PCBs can be freely designed to fit and fulfill the designated roles as well as be adapted to changing and higher capacity components.
- Please note that that said media are fully responsible for their own thermal regulation, as drives may not have any airflow or limited cooling capability on their own.
  - It is however encouraged to use available cooling options espechally in "drive arrays" and "autoloader" configurations where media are expected to be written to 24/7 and/or constantly at their maximum speeds.
    - Drive Arrays and Autoloaders must account for the media heating up and should therefore provide adequate airflow for cooling.
    - Contact-based cooling is not officially supported, thus must account for the risk of condensation.
    - Submerging in liquid coolant is not supported as per standard.
      - Drives and Media doing so must explicitly state this function and should only be used in such a configuration if supported.
- The total interior vertical height is 2,2mm. This includes the entire PCB and all it's components as well as any "Thermal Interface Material" (TIM) used.

##  Electrical Standards
Utilizing the benefits of the 3,5" FDD mechanical form factor - including the shutter as a base, the NeoFloppy media uses [LGA](https://en.wikipedia.org/wiki/Land_grid_array) as means for the media to electromechanically connect to the host system.
- Instead of a read/write head that moves along a classic floppy media, the head consists of an LGA "Socket" with it's spring-loaded micro-pins [similar to pogo-pins] that only moves vertically to [dis-]connect electrically.
- Unlike SATA, SAS, U.2 and other internal drive connectors, this is intended to last > 10.000 cycles.

### Head Window
The Head Window is the name for the contact area protected by the shutter .
- It's dimensions are 23,8 x 8,8mm, which is in line with the 3,5" FDD's Window as per ECMA-125.

### Contact Area
In the middle of the Head Window, the contact window of 1mm spaced LGA pads in a 8x23 pin raster, providing a total of 184 pins for contact.

####  Pinout
The Pinout is from top front as of direction of insertion to the rear

PIN| 0           | 1         | 2         | 3               | 4               | 5              | 6               | 7
---|-------------|-----------|-----------|-----------------|-----------------|----------------|-----------------|---
A  | PRSNT#0     | GND       | 5V        | 5V              | 3,3V            | 3,3V           | GND             | PRSNT#1
B  | USB_VBUS_5V | USB2_D-   | USB2_D+   | USB3_StdA_SSRX- | USB3_StdA_SSRX+ | USB3_GND_DRAIN | USB3_StdA_SSTX- | USB3_StdA_SSTX+ 
C  | SD_CD/DAT3  | SD_CMD    | SD_VSS1   | SD_VDD          | SD_CLK          | SD_VSS2        | SATA_B+         | WRITE_ENABLE
D  | SD_DAT0     | SD_DAT1   | SD_DAT2   | SATA_GND        | SATA_A+         | SATA_A-        | SATA_B-         | WRITE_PROTECT
E  | PCIe_GND    | PCIe_GND  | PCIe_GND  | PCIe_RESET#     | PCIe_GND        | PCIe_GND       | PCIe_GND        | READ_ENABLE
F  | PCIe_GND    | PCIe0_TX+ | PCIe0_TX- | PCIe_GND        | PCIe0_RX+       | CIe0_RX-       | PCIe_GND        | CFG_#0
G  | PCIe_GND    | PCIe_GND  | PCIe_GND  | PCIe_WAKE#      | PCIe_GND        | PCIe_GND       | PCIe_GND        | CFG_#1
H  | PCIe_GND    | PCIe1_RX- | PCIe1_RX+ | PCIe_GND        | PCIe1_TX-       | PCIe1_TX+      | PCIe_GND        | CFG_#2
I  | PCIe_GND    | PCIe_GND  | PCIe_GND  | PCIe_REFCLKN    | PCIe_GND        | PCIe_GND       | PCIe_GND        | CFG_#3
J  | PCIe_GND    | PCIe2_TX- | PCIe2_TX+ | PCIe_GND        | PCIe2_RX-       | PCIe2_RX+      | PCIe_GND        | CFG_#4
K  | PCIe_GND    | PCIe_GND  | PCIe_GND  | PCIe_REFCLKP    | PCIe_GND        | PCIe_GND       | PCIe_GND        | CFG_#5
L  | PCIe_GND    | PCIe3_RX- | PCIe3_RX+ | PCIe_GND        | PCIe3_TX-       | PCIe3_TX+      | PCIe_GND        | CFG_#6
M  | PCIe_GND    | PCIe_GND  | PCIe_GND  | SYSCLK#         | PCIe_GND        | PCIe_GND       | PCIe_GND        | CFG_#7
N  | PCIe_GND    | PCIe4_TX- | PCIe4_TX+ | PCIe_GND        | PCIe4_RX-       | PCIe4_RX+      | PCIe_GND        | CFG_#8
O  | PCIe_GND    | PCIe_GND  | PCIe_GND  | PRSNT_#2        | PCIe_GND        | PCIe_GND       | PCIe_GND        | WRITE_STOP
P  | PCIe_GND    | PCIe5_RX- | PCIe5_RX+ | PCIe_GND        | PCIe5_TX-       | PCIe5_TX+      | PCIe_GND        | WRITE_COMPLETE
Q  | PCIe_GND    | PCIe_GND  | PCIe_GND  | PRSNT_#2        | PCIe_GND        | PCIe_GND       | PCIe_GND        | EJECT_READY
S  | PCIe_GND    | PCIe6_TX- | PCIe6_TX+ | PCIe_GND        | PCIe6_RX-       | PCIe6_RX+      | PCIe_GND        | EJECT_REQUEST
T  | PCIe_GND    | PCIe_GND  | PCIe_GND  | PRSNT_#3        | PCIe_GND        | PCIe_GND       | PCIe_GND        | READ_STOP
U  | PCIe_GND    | PCIe7_RX- | PCIe7_RX+ | PCIe_GND        | PCIe7_TX-       | PCIe7_TX+      | PCIe_GND        | MEDIA_READY
V  | PCIe_GND    | PCIe_GND  | PCIe_GND  | PCIE_WAKE#      | PCIe_GND        | PCIe_GND       | PCIe_GND        | VOLTAILE_ENABLE
W  | PRSNT#1     | GND       | 3,3V      | GND             | 1,8V            | GND            | PRSNT#3         | PRSNT#0

##### Glossary
- PRSNT# is the media presence detection. Those pins pairs just connect through to each [PRSNT#X-PRSNT#X] to enshure proper alignment of the mead.
- USB_ stands for the Pins as per "USB 3.1 Gen 2" for a maximum of 10Gbit/s transfer speed.
- SD_ Stands for the Pins as per 
- PCIeX_YYz stands for PCIe Lane X [0-7], Direction YY [RX/TX], Polarity [+/-].
- PCIE_ stands for auxilliary PCIe signals, like PCIe_GND is the shielding ground for PCIe signals.

###### Status Pins
All Status pins use 0-2V for low and 2,7-5,5V for high

Read- & Writeability:
- READ_ENABLE [RE], WRITE_ENABLE [WE], WRITE_PROTECT [WP] & VOLTAILE_ENABLE [VE] define cartridge parameters

RE | WE | WP | VE | Media Type  | Comment
---|----|----|----|-------------|---
0  | 0  | 1  | 1  | Cleaning    | Cleaning Cartridge - Distingushable from ROM Cartridges                            
1  | 0  | 1  | 0  | ROM         | Can only be read                                                                   
1  | 1  | 0  | 0  | Rewriteable | Can be accessed like any other rewriteable media                                   
0  | 1  | 0  | 0  | WOM         | Write-Only memory [WORM media that are configured to be write-only]                
0  | 0  | 0  | 0  | media error | to be interpreted as either faulty media or if PRSNT#x fail as "media not present" 
1  | 1  | 0  | 1  | RAM         | RAM-based/voltaile media
1  | 0  | 1  | 1  | VROM        | RAM-based ROM Media [i.e. VWORM or similar media]
0  | 1  | 0  | 1  | VWOM        | RAM-Based WOM [WORM media that are configured to be write-only]  

RAM-based / voltaile media can employ a battery backup.
- In that case, they've to make said battery tool-free removeable and add a switch at the rear to allow for wiping the contents by disconnecting the battery circuit.
  - a rechargeable R616 cell is recommended, tho the individual implementation is up to the manufacturer.
- RAM Media that don't have any backup battery must state so clearly on the packaging.
  - The battery lifetime and shelf-life as well as instructions on how to replace and - if applicable - recharge the battery must be included in the datasheet of the media.

Media Status:

These pins indicate various statuses to be interpreted by the drive / media

Status         | Set by | Comment
---------------|--------|---
EJECT_REQUEST  | Host   | Media should prepare for graceful dismount and eject.
EJECT_READY    | Media  | The Media can now be safely ejected.
MEDIA_READY    | Media  | Media is uninitialized / idle in the drive.
READ_STOP      | Host   | Abort all access operations of the drive.
WRITE_STOP     | Media  | Writing to the media should be stopped.
WRITE_COMPLETE | Media  | All Data has been written to the medium.

Insertion Sequence:
1. Media is placed in the drive.
2. Drive head is contacting the Media. 
3. Drive detects PRSNT#-Pins are connected. 
4. Drive provides power to voltage pins. 
5. Media reports MEDIA_READY. 
6. Drive checks configuration and enable pins and selects one of the available interfaces. 
7. Regular Drive Access.

NOTE:
- Compliant Media must report MEDIA_READY within 1 second of having voltage applied to the contacts.
  - This is to enshure reliable detection of faulty Media.
- Compliant Media and Drives must complete the insertion sequence within 5 seconds.
  - Meaning that within the 5 seconds the media must be inserted and available to the Host Operating System as a mountable device & filesystem.
  - This is to enshure detection of faulty media and/or faulty drives.

Ejection Sequence:
1. Host / Drive sends EJECT_REQUEST to Media.
2. Media replies with WRITE_STOP [even on read-only media].
3. Host confirms with READ_STOP [even on write-only media].
4. Media confirms all actions complete with WRITE_COMPLETE [even on read-only media].
5. Once dismounted by the host, media confirms with EJECT_READY.
6. The host can then safely eject the media by sending a command to the drive.
7. The drive head will be retracted and thus disconnected.
8. If a media is not ejected it can be reconnected without ejection. [like on an ODD]

NOTE:
- Compliant Media must complete the Ejection Sequence till EJECT_READY within 2 seconds.
  - This is to enshure the graceful ejection.
  - This sequence is allowed to fail if the Host Operating System still commences read/write access.
    - Thus this is a safeguard to prevent data loss and system crashes in case the Operating System is running from said media.
- Compliant Media and Drives must complete the ejection sequence within 5 seconds, unless failed.
  - This is to detect faulty media and/or drives unless media and/or drives are still busy.

###### Configuration Pins
Pins 0-7 are configureable
- Pin 0: Active Media [Only low on Testing Cartridges]
- Pin 1: Useable Media [Only low on Cleaning cartridges]
- Pin 2: USB Interface Supported [only low on cleaning Cartridges]
- Pin 3: SD Interface Supported [only low on media that explicitly don't!]
- PIN 4: SATA Interface Supported [only low on media that explicitly don't!]
- PIN 5-7: PCIe Interface Supported [only low on media that explicitly don't!]
- PIN 8: WORM Media [must be explicitly designated as such]

#5 | #6 | #7 | Lanes
---|----|----|---
 0 | 0  | 0  | 0
 1 | 0  | 0  | 1
 1 | 1  | 0  | 2
 1 | 0  | 1  | 4
 1 | 1  | 1  | 8

NOTE:
- Not every drive and media supports all interfaces.
  - The minimum viable media supports USB 3.1 Gen 2 only, tho producing such media is discouraged.
- It is recommended to support as many interface types as possible.
  - Implementation Freedom was given with the intent to allow for both cheap & low-bandwith as well as performance-oriented media.
    - SD for low-power embedded devices that may not support [booting from] USB.
    - USB as common denominator and for affordable mass-market external drives that allow for convenience.
    - SATA for portable bootable setups and easy archivability of a full system, espechally when setup of such a system may be tideous and/or time-consuming beyond reason.
    - PCIe for high performance use cases.
- RFID & NFC Tags should be read by every drive.
  - NFC Tag Writeability and Barcode / QR-Code readability is optional, tho also recommended - espechally for media libraries.


##  Software & Data Layout
###   Filesystems
As per definition as an Open-Source Format, compliant media can only e shipped with open-source licensed filesystems.
- Since the NeoFloppy is low-level adressible, it is only discouraged as violation of specification, but not impossible to use any other filesystem one is capable to format it into.
- Compliant Media thus will only be formatted from the factory with approved filesystems.

As of now the following Filesystems are approved:
- [LTFS](https://en.wikipedia.org/wiki/Linear_Tape_File_System)
  - as per [Reference Implementation](https://github.com/LinearTapeFileSystem/ltfs)
  - To be used with WORM media.
- [OpenZFS](https://en.wikipedia.org/wiki/OpenZFS)
  - since Oracle's [ZFS](https://en.wikipedia.org/wiki/ZFS) isn't Open-Source - licensed anymore.
  - To be used with multisession/append-only rewriteable media through versioned snapshots.
- [Btrfs](https://en.wikipedia.org/wiki/Btrfs)
  - As it's a good and well-performing filesystem for allround use
- [ext4](https://en.wikipedia.org/wiki/Ext4)
  - Compatible with Windows using [WSL2](https://en.wikipedia.org/wiki/Ext4#Compatibility_with_Windows_and_Macintosh)
- [ext2](https://en.wikipedia.org/wiki/Ext2)
  - To be used in embedded devices in lieu of [FAT32](https://en.wikipedia.org/wiki/File_Allocation_Table#Patents), [ExFAT](https://en.wikipedia.org/wiki/ExFAT) & [NTFS](https://en.wikipedia.org/wiki/NTFS) due to their [legal status](https://en.wikipedia.org/wiki/ExFAT#Legal_status) and Anti-FLOSS - stance of it's maintainer, Microsoft.
- [ISO9660](https://en.wikipedia.org/wiki/ISO_9660)
  - to be used exclusively with ROM media.
  - [Joliet](https://en.wikipedia.org/wiki/ISO_9660#Joliet) &  [Apple Extensions](https://en.wikipedia.org/wiki/ISO_9660#Apple_extensions) are to be supported.
- [tmpfs](https://en.wikipedia.org/wiki/Tmpfs)
  - to be used exclusively with RAM media.

The following Filesystems are under consideration:
- [XFS](https://en.wikipedia.org/wiki/XFS)
  - once [Guaranteed rate I/O](https://en.wikipedia.org/wiki/XFS#Guaranteed-rate_I/O) is available and implemented in other systems than proprietary & custom [IRIX](https://en.wikipedia.org/wiki/IRIX) based workstations and servers.
- [F2FS](https://en.wikipedia.org/wiki/F2FS)
  - once it's current limits of 16 TiB per volume and 3,94 TiB per file have been significantly lifted.
- [Bcachefs](https://en.wikipedia.org/wiki/Bcachefs) 
  - lack of support outside of Linux is hampering it.
- [NOVA](https://en.wikipedia.org/wiki/NOVA_(filesystem))
  - to be used for [NVDIMM](https://en.wikipedia.org/wiki/NVDIMM) and other NVRAM technology such as [MRAM](https://en.wikipedia.org/wiki/Magnetoresistive_RAM), [Nano-RAM](https://en.wikipedia.org/wiki/Nano-RAM) and [3D XPoint](https://en.wikipedia.org/wiki/3D_XPoint).
- [EROFS](https://en.wikipedia.org/wiki/EROFS)
  - to be used for ROM media exceeding the maximum size of ISO9660, which is 8 TiB as of day of writing.
- [SquashFS](https://en.wikipedia.org/wiki/SquashFS)
  - to be used for ROM media in conjunction with [Union Mount](https://en.wikipedia.org/wiki/Union_mount) to provide a transparent [pseudo-] writeable filesystem when read-only setups are not supported in a traditional manner.
- [NILFS2](https://en.wikipedia.org/wiki/NILFS)
  - lack of support outside of Linux is hampering it.
- [APFS](https://en.wikipedia.org/wiki/Apple_File_System)
  - lack of support outside of Apple's ecosystem is hampering it.

###   Media Encryption
#### Supported Use
By default, all media should be transparently encryptable using [LUKS2](https://en.wikipedia.org/wiki/Linux_Unified_Key_Setup) / [dm-crypt](https://en.wikipedia.org/wiki/Dm-crypt).
- Alternatively, included encryption within said filesystems can be used.
  - This is supported in LTFS & OpenZFS as per their specification.

##### Important Note
- The use of alternative encryption methods (regardless if Software like [VeraCrypt](https://en.wikipedia.org/wiki/VeraCrypt) or proprietary Hardware Standards like [OPAL](https://en.wikipedia.org/wiki/Opal_Storage_Specification)) is a violation of specification and thus not endorsed as only fully open-sourced encryption can be trusted.
  - The use of proprietary & non-FLOSS'd solutions like [BitLocker](https://en.wikipedia.org/wiki/BitLocker) is a [clear violation](https://en.wikipedia.org/wiki/BitLocker#Upholding_Kerckhoffs's_principle) of [basic principles](https://en.wikipedia.org/wiki/Kerckhoffs%27s_principle) in cryptography and should never be supported, but clearly discouraged.

### Data Layout
To enable maximum flexibility and future-proof design, the exact layout of the data is up to the used media.
- A media should always apprear as one contigous blockdevice to the host, regardless of the underlying storage technology or media organization used.
- The use of transparent error correction, wear leveling, reserve blocks and even redundancy with transparent RAID modi is recommended, but entirely optional.
  - Media must detail these features in their datasheet.
- Functionalities like ROM and WORM media must be implemented low-level and transparently, so that even faulty drives trying to [re-]write on them can't if that's not permitted.

##  Drives
### Functionality
####  Mandatory Functions
- Buttons
  - "Pause" button [to initialize Ejection Sequence]
  - "Eject" button [to mechanically remove media]
  - Buttons may be absent on autoloaders and drives that provide support for these in Software.
    - Compareable to motorized / software-controlled "auto eject" on Macintosh.
- Status Indicators
  - "Power" [drive is powered]
    - This is only mandatory for external drives that aren't integrated into a system.
  - "Media Inserted" [if a Media has been detected]
    - This should blink fast if a faulty media has been inserted.
    - This should blink slow if a cleaning or test media has been inserted.
  - "Media Online" [if a media is currently connected via the drive head]
    - This should blink to signal "Media Busy" [read/write access is commencing]
  - These can be dedicaded or colour-changing LEDs or a small OLED showing a message.
    - These may be absent on autoloaders and media libraries which should provide the functionality in Software and a dedicaded OLED/LCD status screen.
- Interfaces
  - USB 3.1 Gen 2
    - This should utilize USB-C on external drives and the USB3 header on internal drives if a SATA/Molex/Floppy power connector is interated in the drive.
      - Otherwise it must use USB-C header connection on internal drives.
    - USB is mandatory to be supported by all drives and media.
  - All other interfaces are optional, but implementation is highly recommended.
    - SATA-6G
      - Slimline-SATA connector is to be used if no additional power cable is to be run to it.
        - An additional Adaptor cable for use with regular SATA-6G connectiors should be supplied in retail packages aimed at desktop setups.
    - PCIe 2.0 and up 
      - For a single PCIe Lane, a [Mini-]PCIe card and extension cable may be used.
        - For external Drives, an ExpressCard/34 connector should be used.
      - For up to two PCIe Lanes, A SATA Express Connector and Cable should be used.
        - For external drives, a Thunderbolt3/USB4 connector & Controller should be used.
      - For up to four PCIe Lanes, A M.2 M-Key "Card" and SFF-8643 cable should be used.
        - For external Drives, an SFF-8644 cable should be used.
          - Optionally, a Thunderbolt3/USB4 connector & Controller can be used in addition.
        - For up to eight PCIe Lanes, a PCIe card with two SFF-8643 cables should be used.
          -  For external Drives, an SFF-8644 duplex/"8x" cable should be used.
      - In all cases, a drive must also support and properly negotiate different numbers of lanes and versions on both ends.
        - I.e. A PCIe 4.0 x8 media in a drive only connected via PCIe 2.0 x4 must negotiate PCIe 2.0 x4 speeds.
        - I.e. A PCIe 5.0 x1 media in a drive only connected via PCIe 4.0 x4 must negotiate PCIe 4.0 x1 speeds.
    - SD
      - Drives can be internally connected directly to the SD bus, if available.
        - Otherwise a USB 3.0 SD cardreader chip should be used.
      - This solely uses the original SD Card bus, tho operates as an SDUC card.
        - SD Express won't be supported
        - UHS-II may be supported in future versions.
  - Multiple / Mixed Interfaces
    - The drive should always negotiate the fastest possible interface supported by both the host and the media.
      - A drive must also support not having all interfaces connected and thus should include DIP switches to skip unused/disconnected interfaces.
    - A low-profile, half-lenght & passively cooled 'standalone' "reference controller card" supporting all interfaces is planned.
      - This reference controller card will be x16 electrically for ease of integration and providing dedicaded lanes for all interfaces supported.
        - USB 3.1 Gen 2
        - SATA-6G
        - PCIe 4.0 x8
        - SD
      - "cost reduced" and simplified options using a lower number of lanes host-side are also possible.
        - Manufacturers of drives and controllers must design their products so that they rely on the least amount of custom parts and cables possible.
          - If a specific drive and/or controller can only be used in conjunction with each other, it must be prominently stated on the packaging, product information and specifications.
            - Whilst such combinations may not be desireable in general and are severely discouraged, they may be necessary in certain embedded & rugged devices.
    - Under all circumstances every media and drive will only use one interface type at the same time.
      - Switching Interfaces without "soft-ejection" & reinitialization is not supported as of now.
        - Doing so would require extensive support by both Operating Systems, Hardware, Software, Firmware and espechally Controller ICs on said media.
          - It may however be supported in the future with specifically designated combinations of Hardware and Software.
      - "Multipath" and "Multi-Host" support has to be provided by backplanes capable of doing so.
        - This feature is to be seen as unsupported but not forbidden.
          - Future versions may allow said feature, but it'll remain optional for drives and media.
    - A drive with multiple/mixed interfaces may also be discreetly connected as mentioned before.
      - Thus it will appear as if a media has been plugged into the negotiated interface directly.
        - This is done to enshure transparent compatibility between Operating Systems and Media.
