#
# Makefile in src
#
include ../Make.properties
TARGET=libtest.a
# subdirs
F1_PATH=f1
F2_PATH=f2
SUBDIRS=$(F1_PATH) $(F2_PATH)

# objs
F1_OBJS=$(F1_PATH)/f1.o
F2_OBJS=$(F2_PATH)/f2.o
TEST_OBJS=$(F2_OBJS) $(F1_OBJS)

all: subdirs $(TARGET)
	mv $(TARGET) $(DISTDIR)

subdirs:
	@for i in $(SUBDIRS); do \
		echo "===> $$i"; \
		(cd $$i && $(MAKE) -f $(MAKEFILE)) || exit 1; \
		echo "<=== $$i"; \
	done

$(TARGET):$(TEST_OBJS)
	ar -r $@ $^

.PHONY:clean
clean:
	@for i in $(SUBDIRS); do \
		echo "===> $$i"; \
		(cd $$i && $(MAKE) clean -f $(MAKEFILE)) || exit 1; \
		echo "<=== $$i"; \
	done
	rm -f $(DISTDIR)/$(TARGET)

