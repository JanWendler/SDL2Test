cmake_minimum_required(VERSION 3.21)
project(SLD2Test)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_EXE_LINKER_FLAGS "-static-libgcc -static-libstdc++")


set(SOURCE_FILES main.cpp)

include_directories(${PROJECT_SOURCE_DIR}/include)
link_directories(${PROJECT_SOURCE_DIR}/lib)
add_executable(SLD2Test ${SOURCE_FILES})
set_target_properties(SLD2Test PROPERTIES COMPILE_OPTIONS "-m32" LINK_FLAGS "-m32")
target_link_libraries(SLD2Test mingw32 SDL2main SDL2 )

find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS})
add_executable(LinuxTest ${SOURCE_FILES})
set_target_properties(LinuxTest PROPERTIES COMPILE_OPTIONS "-m32" LINK_FLAGS "-m32")
target_link_libraries(LinuxTest ${SDL2_LIBRARIES})