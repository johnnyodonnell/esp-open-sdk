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

Based on this stackoverflow question:
https://stackoverflow.com/questions/9922949/how-to-print-the-ldlinker-search-path
it looks like -ldriver is being found in the directory:
/opt/Espressif/esp-open-sdk/xtensa-lx106-elf/xtensa-lx106-elf/sysroot/usr/lib
I found this by running the gcc linker with the "-v" flag. In other words,
I added "-v" do the varaible LDFLAGS

