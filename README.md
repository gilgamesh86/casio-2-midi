# Casio 2 Midi!!!

#### The main purpose of this project was to validate the Casio's key matrix for my synth.

## Overview

It uses standard matrix scanning algorithm. The model of the Casio is SA-77, having total of 44 keys. Its key matrix has 14 total pins making a **8x6 matrix**. Scan rate is 500hz via a timer interrupt. 

For the USB part, the type of transmission for the Midi class is same as CDC class, so I used CubeMX's generated middleware for Midi class and changed the descriptors. [This](https://www.usb.org/sites/default/files/midi10.pdf) is the link to the doc I used for reference.

I kept the rest of the middleware same except changing the config descriptor size, and adding midiTxBusy flag in the USBD_CDC_DataIn function in the usbd_cdc.c file, to avoid missed notes.


If you want to check out the synth project (WIP) it's [here](https://github.com/gilgamesh86/synthV1).
