cmake_minimum_required(VERSION 3.5)

add_executable(evio2xml evio2xml.cc)
target_link_libraries(evio2xml 
  evio
  EVIO::EVIOcpp
  )

add_executable(evioCat evioCat.cc)
target_link_libraries(evioCat 
  evio
  EVIO::EVIOcpp
  )

add_executable(eviocopy eviocopy.c)
target_link_libraries(eviocopy 
  evioStatic
  )

add_executable(xml2evio eviocopy.c)
target_link_libraries(xml2evio 
  evioStatic
  )

install(TARGETS evio2xml evioCat eviocopy xml2evio
    EXPORT evio-targets
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)

#
#eviocopy.c
#old.evio2xml.c
#xml2evio.c
