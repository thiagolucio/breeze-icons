if(BINARY_ICONS_RESOURCE)
    generate_binary_resource(icons binary_resource)
endif()

########### install files ###############

set( breeze_icon_dirs  actions applets apps categories devices emblems emotes mimetypes places status )

set(BREEZE_INSTALL_DIR ${KDE_INSTALL_FULL_ICONDIR}/breeze)

if (NOT SKIP_INSTALL_ICONS)
    install( DIRECTORY ${breeze_icon_dirs} DESTINATION ${BREEZE_INSTALL_DIR} )
    install( FILES index.theme DESTINATION ${BREEZE_INSTALL_DIR})
endif()

gtk_update_icon_cache(${BREEZE_INSTALL_DIR})

if(BINARY_ICONS_RESOURCE)
    install( FILES ${binary_resource} DESTINATION ${BREEZE_INSTALL_DIR})
endif()
