include ../../../inc/common.mk

L += $(MYSQLLIBS) -lm
MYLIBDIR = ../../../lib/$(MACHTYPE)
MYLIBS =  $(MYLIBDIR)/jkhgap.a $(MYLIBDIR)/jkweb.a

O = omimParseRec.o

omimParseRec: $O $(MYLIBS)
	${CC} ${COPT} ${CFLAGS} -o ${BINDIR}/omimParseRec $O $(MYLIBS) $L
#	${STRIP} ${BINDIR}/omimParseRec${EXE}

test: test1 
%:	input/%
	${MKDIR} output/$@
	omimParseRec input/$@ output/$@
	diff -x CVS -r expected/$@ output/$@
	rm -r output

clean::
	rm -f ${O}
