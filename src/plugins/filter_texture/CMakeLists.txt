include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}
  )

QT5_WRAP_CPP(moc_files filter_texture.h)

set(filter_texture_SRCS
  filter_texture.cpp
  ../../other/vcglib/wrap/ply/plylib.cpp
  ${moc_files}
  )

add_library(filter_texture SHARED ${filter_texture_SRCS})
target_link_libraries(filter_texture ${QT_LIBRARIES} ${OPENGL_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})
install(TARGETS filter_texture
  RUNTIME DESTINATION ${BIN_DIR}
  LIBRARY DESTINATION ${LIB_DIR}
  ARCHIVE DESTINATION ${LIB_DIR})

# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8
