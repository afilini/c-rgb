SRCS = $(wildcard *.c)
BUILDDIR = ./build
BINARIES = $(SRCS:%.c=${BUILDDIR}/%)

.PHONY: clean

MKDIR_P = mkdir -p
CC := gcc

LDFLAGS := -L../target/debug/
CFLAGS := -g -static -lrgb -lpthread -ldl -lm -Wall -Wextra -I../include/

all: dir $(BINARIES)

dir:
	$(MKDIR_P) ${BUILDDIR}

clean:
	$(RM) -r ${BUILDDIR}

$(BINARIES) : ${BUILDDIR}/% : %.c ../target/debug/librgb.a ../include/rgb.h
	$(CC) $< $(CFLAGS) $(LDFLAGS) -o $@
