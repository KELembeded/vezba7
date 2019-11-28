sources=$(wildcard *.c)
objs=$(sources:.c=.o)
# Ovde postaviti ime izvrsnog fajla: result=ime_izvrsnog_fajla
result=izvrsni

all: $(result)
$(result): $(objs)
	@echo -n "Building output binary: "
	@echo $@
	$(CC) -o $@ $(objs)
%.o: %.c
	@echo -n "Compiling source into: "
	@echo $@
	$(CC) -c $<
%.d: %.c
	@echo -n  "Creating dependancy: "
	@echo $@
	@rm -f $@; \
	$(CC) -MM $(CPPFLAGS) $< > $@;
-include $(sources:.c=.d)
.PHONY: clean
clean:
	@rm -rf $(result) *.o *.d
	@echo "Clean done.."
