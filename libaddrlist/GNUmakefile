
TARGETLIB=	libaddrlist.a

SRCS+=		addresses.c

CFLAGS+=	-O2
CFLAGS+=	-Wall
CFLAGS+=	-Wno-address-of-packed-member

OBJS+=	$(SRCS:%.c=%.o)

.PHONY: clean

all: $(TARGETLIB)

$(TARGETLIB): $(OBJS)
	$(AR) $(ARFLAGS) $@ $^

test: libaddrlist.a
	cc test.c libaddrlist.a && ./a.out

depend:
	mkdep $(SRCS)

clean:
	rm -f $(TARGETLIB) $(OBJS)

cleandir: clean
	rm -f a.out
	rm -f .depend GPATH GRTAGS GSYMS GTAGS

install:

-include .depend
