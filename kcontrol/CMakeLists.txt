
########### next target ###############

set(kcm_kamera_PART_SRCS kamera.cpp kameradevice.cpp kameraconfigdialog.cpp )

add_library(kcm_kamera MODULE ${kcm_kamera_PART_SRCS})

include_directories(${GPHOTO2_INCLUDE_DIRS} ${CMAKE_BINARY_DIR})

target_link_libraries(kcm_kamera
    KF5::ConfigWidgets
    KF5::XmlGui
    KF5::KIOCore
    KF5::I18n
    KF5::ConfigCore
    ${GPHOTO2_LIBRARIES}
    )

install(TARGETS kcm_kamera  DESTINATION ${PLUGIN_INSTALL_DIR} )


########### install files ###############

install( FILES kamera.desktop  DESTINATION  ${SERVICES_INSTALL_DIR} )
