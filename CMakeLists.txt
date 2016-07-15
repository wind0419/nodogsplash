CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(nodogsplash C)

add_definitions(-Os -Wall)

# libraries pthread + libmicrohttpd
set(LIBS pthread)

find_package(PkgConfig)
PKG_CHECK_MODULES(MHD libmicrohttpd REQUIRED)
include_directories(${MHD_INCLUDE_DIRS})
set(LIBS ${LIBS} ${MHD_LIBRARIES})


if(DEBUG)
  add_definitions(-DDEBUG -g3)
  if(NO_OPTIMIZE)
    add_definitions(-O0)
  endif()
endif()

add_subdirectorY(src)
