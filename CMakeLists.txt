cmake_minimum_required(VERSION 3.1...3.28)

project(
  jemalloc 
  VERSION 1.0
  LANGUAGES CXX)

add_custom_target(nuke
	COMMAND make clean
        WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
)

add_custom_target(jemalloc ALL
	COMMAND ./autogen.sh --disable-initial-exec-tls COMMAND make
        WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
)
