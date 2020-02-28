cmake_minimum_required (VERSION 3.8)
project (vec
    VERSION 0.2.2
    LANGUAGES C)    

 add_library(${PROJECT_NAME} src/vec.c src/vec.h)
 
 target_include_directories(${PROJECT_NAME} PUBLIC
  $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/src>
  $<INSTALL_INTERFACE:src>)
  
set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)
 target_link_libraries (${PROJECT_NAME} pthread)