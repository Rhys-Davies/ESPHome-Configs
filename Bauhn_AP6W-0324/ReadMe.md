Bauhn AP6W-0324 - 6 Way Powerboard

MCU: Tuya CB2S (BK7231N)

Firmware version v1.0.4 can be re-flashed using Tuya-CloudCutter: https://github.com/tuya-cloudcutter/tuya-cloudcutter 

Metering Chip: Chipsea CSE7759B
    - UART, 4800Bps, 8 bits, 1 bit even check, 1 bit stop

Note: Green LED is active whenever AC is present.

CB2S Pinout:
* RX1 -> TX of CSE7759B
* TX1 -> RX of CSE7759B
* P24 -> Input (Pulled up) - Power button
* P26 -> Output - Relay
* CEN -> N/C
* ADC -> N/C
* P8 -> Status LED (Blue LED)
* P7 -> N/C
* P6 -> N/C
