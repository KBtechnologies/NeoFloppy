#   NeoFloppy
Specification

Version 0.1

## Goal
The NeoFloppy aims to be a modern removeable media format & standard taking lessions learned from the 1st 3,5" FDD up to present-day SSDs & [NV-]RAM media and developing an easy to handle and use media format.
### Media Types
The following Types of NeoFloppy are specified:
- [WORM](https://en.wikipedia.org/wiki/Write_once_read_many)
  - Specifically for append-only archival media.
- [ROM](https://en.wikipedia.org/wiki/Read-only_memory)
- [RAM](https://en.wikipedia.org/wiki/RAM_drive#Dedicated_hardware_RAM_drives) / Voltaile Memory
- Re-Writeable
  - These may be SSD and/or NVRAM-based and will combine the advantages of USB flashdrives, 2,5" SSDs and 3,5" FDDs without any disadvantages.
- Cleaning Media
  - These don't contain any electrical contacts but are designed to clean the heads of drives.
  - A subsequent "cleaning drive" to clean media is also planned, tho unless physical damage has been exerted onto the media, it should be easily cleanable with 99% isopropylic alcohol and a non-static & fine-tipped sponge-swab.
    - Rare cases of severly gunked-up disks and/or drives will like "Kontakt Chemie LR PCC" or similar Printed Circuit Board Cleaner if not ultrasonic cleaning.
  - The need for any cleaning should be negligible [1x each 5-10 years] per drives and non-zero for media given they get handled properly as per manufacturer specification.
### Why another media type?
#### Longevity
All common external media either suffer from being extremely delicate on their own [i.e. blu-ray disks], having a limited numer of connection cycles as per interface [i.e. 2,5" SSDs] or havr accute mechanical hazard of breaking off their connectors and/or destroying the ports connected to if not the entire machine the port belongs to [i.e. USB flashdrives].


##  Mechanical Dimensions
###    Media
Unless specified otherwise, the media should follow the [ECMA-125](https://www.ecma-international.org/wp-content/uploads/ECMA-125_1st_edition_december_1987.pdf) dimension standards.
####   Casing
Overall:    93,7 x 90,0 x 3,3 mm.
- Identical with 3,5" FDDs
  - Spindle in the middle is not existing - instead it's bottom side is flat and used to place the back label on
  - Holes identical to 1.440kB FDD
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
- Instead of a read/write head that moves along a classic floppy media, the head consists of an LGA "Socket" that only moves vertically to [dis-]connect electrically.
- Unlike SATA, SAS, U.2 and other internal drive connectors, this is intended to last > 10.000 cycles.

The "Head Window" dimensions are 23,8 x 8,8mm.



##  Software & Data Layout
####   Filesystems
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

####   Media Encryption
##### Supported Use
By default, all media should be transparently encryptable using [LUKS2](https://en.wikipedia.org/wiki/Linux_Unified_Key_Setup) / [dm-crypt](https://en.wikipedia.org/wiki/Dm-crypt).
- Alternatively, included encryption within said filesystems can be used.
  - This is supported in LTFS & OpenZFS from the get-go.

##### Important Note
- The use of alternative encryption methods (regardless if Software like [VeraCrypt](https://en.wikipedia.org/wiki/VeraCrypt) or proprietary Hardware Standards like [OPAL](https://en.wikipedia.org/wiki/Opal_Storage_Specification)) is a violation of specification and thus not endorsed as only fully open-sourced encryption can be trusted.
  - The use of proprietary & non-FLOSS'd solutions like [BitLocker](https://en.wikipedia.org/wiki/BitLocker) is a [clear violation](https://en.wikipedia.org/wiki/BitLocker#Upholding_Kerckhoffs's_principle) of [basic principles](https://en.wikipedia.org/wiki/Kerckhoffs%27s_principle) in cryptography and should never be supported, but clearly discouraged.

