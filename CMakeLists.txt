
# Author: TheFrenchLeaf https://github.com/TheFrenchLeaf

CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(CXSparse C)

INCLUDE_DIRECTORIES(./
./Include)

FILE(GLOB CXSparse_SRCS "Source/*.c")
set_source_files_properties(${CXSparse_SRCS} PROPERTIES LANGUAGE C)
add_definitions(-DNCOMPLEX)

ADD_LIBRARY(CXSparse ${CXSparse_SRCS})
if(UNIX)
  TARGET_LINK_LIBRARIES(CXSparse m)
ENDIF(UNIX)

ADD_SUBDIRECTORY(Demo)
