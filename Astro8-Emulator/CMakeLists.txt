cmake_minimum_required(VERSION 3.0 FATAL_ERROR)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O3")

project(astro8)

SET(programName astro8)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/CMakeFiles/")

add_executable (astro8 main.cpp color.hpp colorprint.h processing.h armstrong-compiler.h )

find_package(SDL2 REQUIRED)
find_package(SDL2_mixer REQUIRED)

include_directories(${SDL2_INCLUDE_DIRS} ${SDL2_MIXER_INCLUDE_DIRS})

target_link_libraries(astro8 m ${SDL2_LIBRARIES} ${SDL2_MIXER_LIBRARIES})

file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/../char_set_memtape
  DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/x64/Release/noise.wav
  DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/x64/Release/square.wav
  DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/x64/Release/triangle.wav
  DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
