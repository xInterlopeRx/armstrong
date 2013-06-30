#
# armstorm (Linux Port)
#

TARGET	= libarmstorm3.so
COBJS	= ../../src/arm.o ../../src/common.o ../../src/thumb_db.o ../../src/thumb.o ../../src/armstorm.o
CC	= gcc
CFLAGS	= -fPIC -O2 -Wall -std=c99

all: clib

clean:
	/bin/rm -rf ../../src/*.o ${TARGET} ../../armstorm.a ./../*.o

clib: ${COBJS}
	${CC} ${CFLAGS} ${VERSION} ${COBJS} -shared -o ${TARGET}
	ar rs ../../armstorm.a ${COBJS}

install: libarmstorm3.so
	install -s ${TARGET} /usr/local/lib
	@echo "... running ldconfig might be smart ..."

.c.o:
	${CC} ${CFLAGS} ${VERSION} -c $< -o $@

