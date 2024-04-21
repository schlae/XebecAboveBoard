# Xebec/Intel Above Board Clone

The Above Board is a memory card for the IBM PC/XT series. It uses an 8-bit ISA
bus connector to provide both extended (XMS) and expanded (EMS) memory. This
design is a copy of Xebec's copy of Intel's original design.

The card supports either 64Kbit or 256Kbit DRAM chips. The mix of XMS/EMS is
configured using the switch bank in the upper right corner.

SW1: Off for 64K, On for 256K DRAM chips
SW2-4: XMS selection. Set according to the amount of memory on your motherboard

| SW2 | SW3 | SW4 | Motherboard RAM |
|-----|-----|-----|-----------------|
| Off | On  | On  | 256KB |
| Off | On  | Off | 320KB |
| Off | Off | On  | 384KB |
| Off | Off | Off | 448KB |
| On  | On  | On  | 512KB |
| On  | On  | Off | 576KB |
| On  | Off | On  | 640KB (No XMS installed) |

SW5-8: Base IO address for page control registers, etc

| SW5 | SW6 | SW7 | SW8 | Address |
|-----|-----|-----|-----|---------|
| On | On | On | On | 0x208 |
| On | On | On | Off | 0x218 |
| On | Off | On | Off | 0x258 |
| On | Off | Off | On | 0x268 |
| Off | On | Off | On | 0x2A8 |
| Off | On | On | Off | 0x2B8 |
| Off | Off | Off | On | 0x2E8 |

The design files are for educational purposes. The board has not been cleaned
up for fabrication and still has a number of DRC errors. A practical modern
XMS/EMS board would use modern SRAM chips instead of a large number of old
and unreliable DRAM chips. This would also obviate the need for the vintage
delay line device that is used to generate the RAS/CAS timing pulses.

There is a single PROM on the board (an 82S131). The contents of it are in
XEBEC1.BIN.

## License

This work is licensed under a Creative Commons Attribution-ShareAlike 4.0
International License. See [https://creativecommons.org/licenses/by-sa/4.0/](https://creativecommons.org/licenses/by-sa/4.0/).


