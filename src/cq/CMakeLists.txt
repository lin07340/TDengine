CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
PROJECT(TDengine)

INCLUDE_DIRECTORIES(inc)
AUX_SOURCE_DIRECTORY(${CMAKE_CURRENT_SOURCE_DIR}/src SRC)

IF (TD_LINUX)
  ADD_LIBRARY(tcq ${SRC})
  TARGET_LINK_LIBRARIES(tcq tutil common taos)
  ADD_SUBDIRECTORY(test)
ENDIF ()
