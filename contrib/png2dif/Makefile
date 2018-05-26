TARGET = png2dif
LIBS = -lws2_32
CC = gcc
CFLAGS = -g -Wall -I./ -I ../../include -I ../../third_party/upng/include -I ../../third_party/adafruit/include 

.PHONY: default all clean

default: $(TARGET)
all: default

OBJECTS = $(patsubst %.c, %.o, $(wildcard *.c))
SRCS    = ../../third_party/upng/src/upng.c
HEADERS = $(wildcard *.h)

%.o: %.c $(HEADERS)
	$(CC) $(CFLAGS) -c $< -o $@ -lws2_32

.PRECIOUS: $(TARGET) $(OBJECTS)

$(TARGET): $(OBJECTS)
	$(CC) $(CFLAGS) $(OBJECTS) $(LIBS) $(SRCS) -o $@ -lws2_32

clean:
	-rm -f $(OBJECTS)
	-rm -f $(TARGET)

