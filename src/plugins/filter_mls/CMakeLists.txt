include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}
  )

QT5_WRAP_CPP(moc_files mlsplugin.h)

set(filter_mls_SRCS
  apss.cpp
  balltree.cpp  
  mlsplugin.cpp         
  rimls.cpp
  apss.tpp              
  mlssurface.tpp
  rimls.tpp
  ${moc_files}
  )

add_library(filter_mls SHARED ${filter_mls_SRCS})
target_link_libraries(filter_mls ${QT_LIBRARIES} ${OPENGL_LIBRARIES} ${CMAKE_THREAD_LIBS_INIT})
install(TARGETS filter_mls
  RUNTIME DESTINATION ${BIN_DIR}
  LIBRARY DESTINATION ${LIB_DIR}
  ARCHIVE DESTINATION ${LIB_DIR})

# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8
