TOP        = ../..
SWIG       = $(TOP)/../preinst-swig
SRCS       =
TARGET     = example
INTERFACE  = example.i
SWIGOPT    =

GPP        = `which g++`
MZC        = test -n "/usr/bin/mzc" && /usr/bin/mzc

check: build
	$(MAKE) -f $(TOP)/Makefile SRCDIR='$(SRCDIR)' mzscheme_run

build:
	$(SWIG) -mzscheme -c++ $(SWIGOPT) $(INTERFACE)
	$(MZC) --compiler $(GPP) ++ccf "-I." --cc example_wrap.cxx
	$(MZC) --linker $(GPP) --ld $(TARGET).so example_wrap.o

clean:
	$(MAKE) -f $(TOP)/Makefile SRCDIR='$(SRCDIR)' mzscheme_clean
