SDCC=sdcc
SDLD=sdld
OBJECTS=blinky.ihx uart.ihx

.PHONY: all clean flash

all: $(OBJECTS)

clean:
	rm -f $(OBJECTS) *.asm *.lst *.rel *.lk *.rst *.sym  *.map *.cdb

flash: $(OBJECT).ihx
	stm8flash -cstlink -pstm8l150 -w $(OBJECT).ihx

%.ihx: %.c
	$(SDCC) -lstm8 -mstm8 --out-fmt-ihx $(CFLAGS) $(LDFLAGS) $<
