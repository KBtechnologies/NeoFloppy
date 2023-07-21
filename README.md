#   NeoFloppy
A new storage media format using modern interfaces.

[You can find the specification here.](docs/neofloppy.specification.md)

##  What & Why
### What does the NeoFloppy not do?
The NeoFloppy isn't an actual floppy, but rather a "stiffy disk":

It's NOT an actual magnetic film medium like the 3,5" FDD, ZIP, LS- HiFD and other "Floppy" formats.
- Including the [MemoryStick Floppy Adapter](https://www.youtube.com/watch?v=dhGl30Ll4vA) made by Sony.

### What is the NeoFloppy instead?
The NeoFloppy is an non-mechanical / solid-state media format optimized for handling, transport, storage, archive and subsequent use.

It is only using the mechanical specification of the 3,5" FDD to a specific extent.

Namely: Drive mechanisms (except the head since the drive only needs to vertically contact pins behind the shutter) and the media dimensions.

### Why build such a thing?
Currently existing removeable media have a lot of disadvantages that most people will not recognize at first glance.

Shure microSDUC cards and USB thumbdrives are faster, more reliable and smaller than any floppy disk, but they have a lot of issues associated with them, like being susceptible to mechanical wear & tear, being ripped off from a USB port or being fried due to ESD since they have exposed contacts.

Furthermore high-performance SSD drives may exist in M.2, U.2 and 2,5" SATA form factors, but these connectors were never designed for a 3-4+ digit plug & unplug cycles. Which is fine for stationary use cases like servers, desktops and even laptops but fully falls flat on studio and professional setups as well as mobile recording and editing workflows.

Being able to passively conduct heat from a medium without compromising it's mechanical stability seems mostly manageable with a sheet-aluminium-based casing where the PCB and chips were given ample of cooling space.

### Why make it Open Source?
All "Floppy Alternatives" mostly died out due to being "Single Vendor" and/or "Single Provider" products.

For example the [iomega Zip Drive](https://en.wikipedia.org/wiki/Zip_drive) [suffered this fate](https://www.youtube.com/watch?v=1pBhEaMp8mw).

Even the 3,5" 2880kB ED-Floppy suffered from this problem.

Thus it is essential to enable everyone to support said media format form the get-go without any complex licensing negotiations via a rent-seeking licensing administration that doesn't provide any added value.

Also the drive itself doesn't reinvent the wheel, but uses common & off-the-shelf standards and recombines them to a efficient new ecosystem.
