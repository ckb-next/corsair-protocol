# `7f NN SS 00` - Write multiple packet stream

When the protocol needs to send a message that is more than a 64-byte packet long, it sends a series of 7f packets containing the data, with an incrementing nonce in NN, and the data length in SS (no more than 60 bytes per packet). This is used in firmware update, for transmitting the firmware packets, and in updating the colours, because there are so many keys.
