# The Corsair HID protocol

This repo is structured into folders by bytes, to facilitate fast lookup.

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).

## What we know so far

All packets have a 64 byte payload, padded with zeroes.
The first four bytes of the command are echoed in the response packet.
The protocol is poll based - the mouse may reply to an `0e` command with an arbitrary amount of `01` events terminated with an `03` event before replying.
The protocol uses USB URB interrupts - URB control packets work on most devices, but not on the K95 Platinum.

- 01 - HID event from device to host.
- 03 - Corsair-specific event from device to host.
- 07 - Write command from host to device - does not get a reply from the board.
- 0e - Read command from host to device - gets a reply from the board.
- 7f - Multiple packet stream from host to device - used as a payload in firmware update and colour update
