SDK_BASE        ?= /opt/Espressif/esp-open-sdk/sdk
SDK_INCDIR      = include driver_lib/include
SDK_INCDIR      := $(addprefix -I$(SDK_BASE)/,$(SDK_INCDIR))

CC = xtensa-lx106-elf-gcc
CFLAGS = -I./include -mlongcalls $(SDK_INCDIR) -DICACHE_FLASH
LDLIBS = -L./lib -lpaho-embed-mqtt3c -nostdlib -Wl,--start-group -lmain -lnet80211 -lwpa -llwip -lpp \
         -lphy -lc -ldriver -Wl,--end-group -lgcc
LDFLAGS = -Teagle.app.v6.ld

blinky-0x00000.bin: blinky
	esptool.py elf2image $^

blinky: blinky.o

blinky.o: blinky.c

flash: blinky-0x00000.bin
	esptool.py write_flash -fm dio 0 blinky-0x00000.bin 0x10000 blinky-0x10000.bin

clean:
	rm -f blinky blinky.o blinky-0x00000.bin blinky-0x10000.bin

