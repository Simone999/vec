cmake_minimum_required (VERSION 3.8)
project (vec
    VERSION 0.2.2
    LANGUAGES C)

 add_library(${PROJECT_NAME} STATIC src/vec.c src/vec.h)

 target_include_directories(${PROJECT_NAME} PUBLIC
  $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/src>
  $<INSTALL_INTERFACE:src>)

 target_link_libraries (${PROJECT_NAME} pthread c)