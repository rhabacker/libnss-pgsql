add_custom_target(nss-pgsql.html
    COMMAND
        xmlto xhtml-nochunks -m ${CMAKE_CURRENT_SOURCE_DIR}/config.xsl ${CMAKE_CURRENT_SOURCE_DIR}/nss-pgsql.xml
    DEPENDS
        config.xsl nss-pgsql.xml
)

#TARGETS	= nss-pgsql.html

#all html: $(TARGETS)

#install-data-local: $(TARGETS)
#	$(mkinstalldirs) $(DESTDIR)$(docdir)
#	$(INSTALL_DATA) nss-pgsql.html $(DESTDIR)$(docdir)
#	$(INSTALL_DATA) $(srcdir)/caution.png $(DESTDIR)$(docdir)

#clean-local:
#	rm -f $(TARGETS)

