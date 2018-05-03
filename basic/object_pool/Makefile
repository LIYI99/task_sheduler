include config.mak

CSRC = object_pool.c
SLSRC = 

COBJS = ${CSRC:%.c=%.o}
SOBJS = ${SLSRC:%.s=%.o}
LOPTS = -g

TARGET = libobject_pool.a

$(TARGET) : $(COBJS) $(SOBJS) 
	$(AR) -r $(TARGET)  *.o

%.o: %.c
	$(CC) -c $(COPS) -I. -o $@ $<

%.o : %.s
	$(CC) -c $(COPS) -I. -o $@ $<

share:
	$(CC) $(COPS) object_pool.c  -shared -o libobject_pool.so
clean :
	/bin/rm -f *.o
	/bin/rm -r *.a
test:
	gcc  $(COPS) -g  test.c $(TARGET)  -o test_object_pool -lpthread




