UNAME := $(shell uname)
CFLAGS += -I../sml/include/ -g -Wall
OBJS = sml_server.o
LIBSML = ../sml/lib/libsml.a

ifeq ($(UNAME), Linux)
LIBS = -luuid -lm
endif

sml_server : $(OBJS) $(LIBSML)
	$(CC) $(CFLAGS) $(OBJS) $(LIBS) $(LIBSML) -o sml_server

%.o : %.c
	$(CC) $(CFLAGS) -c $^ -o $@

.PHONY: clean
clean:
	@rm -f *.o
	@rm -f sml_server
