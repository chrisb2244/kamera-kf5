
########### next target ###############

set(kio_kamera_PART_SRCS kamera.cpp )

add_library(kio_kamera MODULE ${kio_kamera_PART_SRCS})

include_directories(${GPHOTO2_INCLUDE_DIRS} ${CMAKE_BINARY_DIR})

target_link_libraries(kio_kamera
    Qt5::Core
    KF5::KIOCore
    KF5::I18n
    ${GPHOTO2_LIBRARIES}
    )

install(TARGETS kio_kamera  DESTINATION ${PLUGIN_INSTALL_DIR} )

########### install files ###############

install( FILES camera.protocol  DESTINATION  ${SERVICES_INSTALL_DIR} )
