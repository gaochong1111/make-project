# Makefile in f1app
include ../../Make.properties
TARGET=runf1

SRC=./src/runf1.cpp



all:
ifeq ($(shell find bin),)
	mkdir bin
endif
	$(CC) -o $(TARGET) $(SRC) $(CPPFLAGS) -L $(DISTDIR) -ltest
	mv $(TARGET) ./bin

clean:
	rm -f ./src/*.o ./bin/$(TARGET)
	rm -R bin
