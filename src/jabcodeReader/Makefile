PREFIX 	=
CC 	= $(PREFIX)gcc
CFLAGS  = -O2 -std=c11 -no-pie

TARGET = bin/jabcodeReader

OBJECTS = $(patsubst %.c,%.o,$(wildcard *.c))

$(TARGET): $(OBJECTS)
	$(CC) $^ -L../jabcode/build -ljabcode -L../jabcode/lib -ljpeg -ltiff -lpng16 -ljbig -llzma -lz -lm $(CFLAGS) -o $@

$(OBJECTS): %.o: %.c
	$(CC) -c -I. -I../jabcode -I../jabcode/include $(CFLAGS) $< -o $@

clean:
	rm -f $(TARGET) $(OBJECTS)
