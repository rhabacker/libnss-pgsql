cmake_minimum_required(VERSION 3.17)

project(libnss-pgsql
    VERSION 1.4.0
    LANGUAGES C
)

find_package(PostgreSQL REQUIRED)

# provide gnu compatible install dirs
include(GNUInstallDirs)

# target install defaults
set(INSTALL_TARGETS_DEFAULT_ARGS
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
)

add_definitions(
    -DSYSCONFDIR="${CMAKE_INSTALL_FULL_SYSCONFDIR}"
    -DHAVE_UNISTD_H
    -DHAVE_NSS_H
)

add_subdirectory(conf)
add_subdirectory(src)
add_subdirectory(doc)

#EXTRA_DIST = acconfig.h doc/Makefile doc/nss-pgsql.sgml doc/nss-pgsql.txt doc/nss-pgsql.ps conf/nsswitch.conf conf/nss-pgsql.conf conf/dbschema.sql nss-pgsql.spec

#doc/nss-pgsql.txt:doc/nss-pgsql.sgml
#	make -C doc text

#doc/nss-pgsql.ps:doc/nss-pgsql.sgml
#	make -C doc postscript


include(FeatureSummary)
feature_summary(WHAT ALL)
