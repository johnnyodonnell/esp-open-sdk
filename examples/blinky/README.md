** Added by johnnyodonnell

For the HiLetgo NodeMCU ESP-12E Module,
the esp_init_data_default.bin must be flashed
before blinky can be flashed. So far I have had
success with flashing the esp_init_data_default.bin
from ESP8266_NONOS_SDK-2.1.0 to the address
0x3fc000. I also successfully flashed using the
esp_init_data_default.bin from ESP8266_NONOS_SDK-2.0.0.
I have not tried flashing these at any different flash
addresses
