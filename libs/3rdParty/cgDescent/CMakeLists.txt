cmake_minimum_required(VERSION 2.6)
project(cgDescent)

IF(UNIX)
  IF(CMAKE_SYSTEM_PROCESSOR MATCHES "x86_64")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fPIC")
  ENDIF()
ENDIF()

INCLUDE_DIRECTORIES(${cgDescent_SOURCE_DIR}/include)
add_library(cgDescent src/cg_descent.cpp)

IF(UNIX)
  IF(CMAKE_SYSTEM_PROCESSOR MATCHES "x86_64")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fPIC")
  ENDIF()
ENDIF()

SET(CMAKE_INSTALL_PREFIX ${CMAKE_SOURCE_DIR})
INSTALL_TARGETS(/lib cgDescent)
