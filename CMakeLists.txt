cmake_minimum_required(VERSION 3.21)
project(SLD2Test)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_EXE_LINKER_FLAGS "-static-libgcc -static-libstdc++")

include_directories(${PROJECT_SOURCE_DIR}/include)
link_directories(${PROJECT_SOURCE_DIR}/lib)

set(SOURCE_FILES main.cpp)

add_executable(SLD2Test main.cpp)
set_target_properties(SLD2Test PROPERTIES COMPILE_OPTIONS "-m32" LINK_FLAGS "-m32")
target_link_libraries(SLD2Test mingw32 SDL2main SDL2 )

add_executable(LinuxTest main.cpp)
set_target_properties(SLD2Test PROPERTIES COMPILE_OPTIONS "-m32" LINK_FLAGS "-m32")
target_link_libraries(SLD2Test SDL2main SDL2 )