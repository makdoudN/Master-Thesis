# MAKEFILE FOR LATEX FILE 
# USING RUBBER
# AUTHOR: MAKDOUD NIZAM
# --------------------------------

PAPER=main  
SHELL=/bin/zsh   # for the while loop below
SRC=$(wildcard *.tex)
OPTS=--pdf --verbose --force

define INFO_PRINT
	echo "\033[0;31m$(1)\033[0m"
endef

.PHONY: clean

all: pdf 


pdf: 
	rubber $(OPTS) $(PAPER) ; \
	bibtex $(PAPER) ;

draft:
	rubber $(OPTS) $(PAPER)

clean:
	rm -f *.log *.aux *.gz *.pdf

watch: 			 # Recompile on update to the source files
	@while [ 1 ]; do; $(call INFO_PRINT, \n ---- Monitoring Latex project \n\n) ;\
					  fswatch -r -0 -1 . ; \
					  sleep 0.01 ; \
					  $(call INFO_PRINT, \n ---- Change detected -->> Recompile Latex Project \n) ; \
					  make all; \
				  done

