# Protocol versions

CUE/NXP devices have a descriptor string with index of 0x4 that contains the protocol version.

Possible values are:

- P00 - "Firmware V1" (< 0x130) URB Controls only.
- P03 - "Firmware V1" interface setup with interrupts. Also used on the Polaris.
- P04 - "Firmware V2" interface setup with interrupts
- P05 - "Firmware V3" interface setup with interrupts

Note: during mouse init, CUE forces P00 for the 0e01 packet and then switches back to the correct P0X version with interrupts.