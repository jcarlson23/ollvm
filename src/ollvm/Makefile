LIBNAME=ollvm
GENERATED=$(LIBNAME)_lexer.mli $(LIBNAME)_lexer.ml $(LIBNAME)_parser.mli $(LIBNAME)_parser.ml 
ASTDIR:=../../../ast
CAMLFLAGS=-I $(ASTDIR)/

SOURCES = \
	$(LIBNAME)_parser.mly \
	$(LIBNAME)_lexer.mll \
	$(LIBNAME)_printer.ml \
	$(LIBNAME)_ez.ml \
	$(LIBNAME).ml

CMI = \
	$(LIBNAME).cmi \
	$(LIBNAME)_ez.cmi \
	$(LIBNAME)_printer.cmi \
	$(LIBNAME)_lexer.cmi

include ../Makefile.common
include .depend

*.mli: $(ASTDIR)/Ollvm_ast.cmo $(ASTDIR)/Ollvm_ast.cmx
*.ml: $(ASTDIR)/Ollvm_ast.cmo $(ASTDIR)/Ollvm_ast.cmx

$(ASTDIR)/Ollvm_ast.cmo:
	make -C $(ASTDIR) Ollvm_ast.cmo

$(ASTDIR)/Ollvm_ast.cmx:
	make -C $(ASTDIR) Ollvm_ast.cmx

$(BYTE): $(CMO) 
	$(CAMLC) -a -o $(LIBNAME).cma $(CMO)

$(NATIVE): $(CMX)
	$(CAMLOPT) -a -o $(LIBNAME).cmxa $(CMX)
