LIBNAME=ollvm_llvmgateway
ASTDIR:=../../../ast
CAMLFLAGS=-I $(ASTDIR)/ -I ../ollvm/ -package llvm

SOURCES = $(LIBNAME).ml
CMI = $(LIBNAME).cmi

include ../Makefile.common
include .depend

$(BYTE): $(CMO)
	$(CAMLC) $(CAMLFLAGS) -a -o $(LIBNAME).cma $^

$(NATIVE): $(CMX)
	$(CAMLOPT) $(CAMLFLAGS) -a -o $(LIBNAME).cmxa $^
