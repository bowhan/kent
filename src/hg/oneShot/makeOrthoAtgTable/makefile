include ../../../inc/common.mk

L += $(MYSQLLIBS) -lm
MYLIBDIR = ../../../lib/$(MACHTYPE)
MYLIBS =  $(MYLIBDIR)/jkhgap.a $(MYLIBDIR)/jkweb.a


O = makeOrthoAtgTable.o

makeOrthoAtgTable: $O ${MYLIBS}
	${CC} ${COPT} -o ${BINDIR}/makeOrthoAtgTable $O ${MYLIBS} $L
	${STRIP} ${BINDIR}/makeOrthoAtgTable${EXE}

clean:
	rm -f $O
