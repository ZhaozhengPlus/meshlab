include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}
  ${CMAKE_CURRENT_SOURCE_DIR}/../../other
  )

QT5_WRAP_CPP(moc_files filter_autoalign.h)

set(filter_autoalign_SRCS
  filter_autoalign.cpp
  ../edit_align/align/AlignPair.cpp
  ../edit_align/align/Guess.cpp
  ../edit_align/point_matching_scale.cpp
  ../../other/vcglib/wrap/ply/plylib.cpp
  ${moc_files}
  )

add_library(filter_autoalign SHARED ${filter_autoalign_SRCS})
target_link_libraries(filter_autoalign ${QT_LIBRARIES} ${OPENGL_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})
install(TARGETS filter_autoalign
  RUNTIME DESTINATION ${BIN_DIR}
  LIBRARY DESTINATION ${LIB_DIR}
  ARCHIVE DESTINATION ${LIB_DIR})

# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8
