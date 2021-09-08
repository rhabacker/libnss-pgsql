

add_library(nss_pgsql MODULE interface.c config.c backend.c util.c)
target_link_libraries(nss_pgsql PRIVATE ${PostgreSQL_LIBRARIES})
target_include_directories(nss_pgsql PRIVATE ${CMAKE_CURRENT_SOURCE_DIR} ${PostgreSQL_INCLUDE_DIRS})
#set_target_properties(nss_pgsql PROPERTIES VERSION ${PROJECT_VERSION} SOVERSION 2)
install(TARGETS nss_pgsql ${INSTALL_TARGETS_DEFAULT_ARGS})

#EXTRA_DIST = nss-pgsql.h

