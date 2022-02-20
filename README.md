# PGA460 LIBRARY
An Arduino based library for ESP32-WROOM-32 to utilise PGA460 series of chips.


# SETUP
The libraray utilises the ESP32's UART2 ports to communicate with the PGA460 chip.
___
If you are using the PGA460PSM-EVM, simply connect the RX of ESP32 to TX of the module and TX of ESP32 to RX of the module with pull-ups to 3.3V. (TTL is not 12V for this module, it is 3.3V to 5V).
___
If you are using the BOOSTXL-PGA460, connect the following:
- TX of ESP32 to UARX (J1, 3*)
- RX of ESP32 to UARX (J1, 4*)
- IO32 of ESP32 to COM_S (J4, 17*)
- IO33 of ESP32 to COM_P (J4, 18*)
- IO25 of ESP32 to MHLD (J4, 36*)
- IO26 of ESP32 to MCS (J4, 37*)

\* - These are not pin numbers of the jumper blocks themselves, but pin number written on the jumper block.

***DO NOT*** connect the BOOSTXL-PGA460 card to the MSP430 launchpad. Set the power mode jumper block (J7) to the external power mode, and used an external 12V power supply.
___
If you are designing your own board, the PGA460 chips' USART port operates at 3.3V to 5V levels, so direct connection is possible without the need for TTL converters.


# TO DO
- Add methods that allow setup of the PGA460 registers without the need to reference the datasheet on how to calculate stuff. (This would particularly alleviate the issues with record time register and temperature read methods)


# CREDITS
This library is based on the Energia library (SLAC741J)[https://www.ti.com/lit/zip/slac741] written by Akeem Whitehead and provided by TI. THe main difference being that this library focuses only on UART communication, and (IMO) exposes the PGA460 chip's functionality in a clearer way.
