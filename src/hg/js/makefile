include ../../inc/common.mk

# recursive target to do install to DEST, with extra excludes EXCL.

JQUERY_FILES=jquery.js jquery.tablednd.js \
    jquery.imgareaselect.js jquery-ui.js jquery.contextmenu.js \
    ui.dropdownchecklist.js \
    jquery.cookie.js jquery.watermarkinput.js \
    jquery.floatheader.js jquery.rotateTableCellContent.js jquery.plugins.js \
    jquery.validate.min.js jquery.history.js
    
JS_FILES=ajax.js alleles.js autocomplete.js edwPersona.js \
    hgCustom.js hgGateway.js hgHubConnect.js hgTracks.js \
    hgVarAnnogrator.js hui.js utils.js ddcl.js subCfg.js \
    encodeProject.js encodeDataSummary.js encodeDataMatrix.js encodeChipMatrix.js encodeMatrix.js \
    ${JQUERY_FILES}

STATIC_FILES=staticDoc.js jquery.js

ifdef LOWELAB
    JS_FILES += lowetooltip.js loweautocomplete.js
endif

user:
	if test -d ${DOCUMENTROOT}-${USER}; then \
	    ${MAKE} doInstall DEST=${DOCUMENTROOT}-${USER}/js; \
	else \
	    ${MAKE} doInstall DEST=${DOCUMENTROOT}/js/${USER}; \
	fi

alpha:
	${GITUP}
	${MAKE} doInstall DEST=${DOCUMENTROOT}/js

beta:
	${GITUP} 
	${MAKE} doInstall DEST=${DOCUMENTROOT}-beta/js extra=-forceVersionNumbers

clean:

compile:

install:
	${MAKE} doInstall DEST=${DOCUMENTROOT}/js

doInstall:
	@mkdir -p ${DEST}/
	../utils/cpAndLinkToResourceFiles.pl ${extra} -exclude='makefile' -versionFile=../inc/versionInfo.h -destDir=${DEST} ${JS_FILES}
	for file in ${STATIC_FILES}; do \
	    cp -p --update $$file ${DEST}; \
	done
