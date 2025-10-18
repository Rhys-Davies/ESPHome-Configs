Bauhn AP5W-0624 - 5 Way Powerboard

    Note: Also appears to be sold as model number APBMC1-0125-5

    Each outlet has individually switched relays

MCU: Tuya CBU (BK7231N)

    - Ground CEN pin to access programming mode

Metering Chip: Belling BL0942

    - UART, 4800Bps, 8 bits, 1 bit even check, 1 bit stop

    - Use ltchiptool to copy tuya firmware and extract cal values before flashing esphome

Note: Green LED is active whenever AC is present.

Recommend retrieving the BL0942 cal values before flashing ESPHome. They are stored in the "key value store" partition.

From the Tuya json schema these are:
* DPS 22: voltage_coe
* DPS 23: electric_coe 
* DPS 24: power_coe 
* DPS 25: electricity_coe

Map to ESPHome cal variables as below:
* voltage_coe -> voltage_reference
* current_coe * 10 -> current_reference
* power_coe / 10 -> power_reference
* electricity_coe -> energy_reference

CBU Pinout:
* RX1 -> BL0942 TX
* TX1 -> BL0942 RX
* RX2 -> N/C
* TX2 -> N/C
* P6 -> Relay 1 (OUT)
* P7 -> Relay 2 (OUT)
* P8 -> Relay 3 (OUT)
* P9 -> Relay 4 (OUT)
* P20 -> N/C
* P22 -> Toggle Button (IN - P/U)
* P24 -> Relay 5 (OUT)
* P26 -> N/C
* P28 -> LED (OUT - Inverted)
* ADC -> N/C
* CEN -> N/C (Ground to access programming mode)


If you forgot to retrieve the cal values prior to flashing, they can be retrieved from a firmware dump. Note that
the cal values will be device specific, make sure you take a firmware dump of each unit before flashing.

See https://docs.libretiny.eu/boards/cbu/#flash-memory-map for partition address offsets. 

Key-Value Store: Start - 0x1D3000, Length - 32 KiB / 0x8000, End - 0x1DB000