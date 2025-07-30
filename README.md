# Simple SDO Transfer in Structured Text
Codesys 2.3 SDO transfer sample using EPEC CANOpen library
# Pre-Requisites
## Hardware
The master device is an EPEC ( epec.fi ) CANOpen enabled PLC running Codesys 2.3.
It has been configured with a recent version of Multitool to be a CANOpen master device.

The slave device is any device that listens to CANOpen Node ID 4, with an write or read/write
object at index 0x2204 and sub-index 1, with a size of 2 bytes.

## CANOpen NMT
The network has been initialized and the NMT state is operational for both devices ( can be done
with the Network tool of multitool, and the addition of a CANOpen device at Node ID 4)

## Software

Runs on Codesys 2.3, and the EPEC CANOpen stack. 

# Function
A counter value is updated every second by checking a TON function block state.
This value will loop back to 0 when overflowing.

This value is passed by address to the SDOTransfer function block.

The SDOTransfer function block is parametered to send the CANOpen frame every second.

The receiving device will receive a new value roughly every second. Precise timing 
is not the goal of either the SDOTransfer FB nor the counter in the Main PRG.


# Sources
https://www.csselectronics.com/pages/canopen-tutorial-simple-intro
https://www.can-cia.org/can-knowledge/network-management
https://epec.fi 
https://www.codesys.com/

# Licence
MIT Licence, (C) 2025 Paul Innovation and Electronics B.V.
