include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}
  )

QT5_WRAP_CPP(moc_files filter_img_patch_param.h)

set(filter_img_patch_param_SRCS
  filter_img_patch_param.cpp
  VisibleSet.cpp
  VisibilityCheck.cpp
  TexturePainter.cpp
  ${moc_files}
  )

add_library(filter_img_patch_param SHARED ${filter_img_patch_param_SRCS})
target_link_libraries(filter_img_patch_param ${QT_LIBRARIES} ${OPENGL_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})
install(TARGETS filter_img_patch_param
  RUNTIME DESTINATION ${BIN_DIR}
  LIBRARY DESTINATION ${LIB_DIR}
  ARCHIVE DESTINATION ${LIB_DIR})

# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8
