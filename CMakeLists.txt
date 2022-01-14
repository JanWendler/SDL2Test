cmake_minimum_required(VERSION 3.21)
project(SLD2Test)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_EXE_LINKER_FLAGS "-static-libgcc -static-libstdc++")

set(SOURCE_FILES main.cpp)

find_package(SDL2 REQUIRED)
include_directories(${PROJECT_SOURCE_DIR}/include)
link_directories(${PROJECT_SOURCE_DIR}/lib)

set(WINDOWS_EXE WindowsTest)
add_executable(${WINDOWS_EXE} ${SOURCE_FILES})
set_target_properties(${WINDOWS_EXE} PROPERTIES COMPILE_OPTIONS "-m32" LINK_FLAGS "-m32")
target_link_libraries(${WINDOWS_EXE} ${SDL2_LIBRARIES})

set(LINUX_EXE LinuxTest)
add_executable(${LINUX_EXE} ${SOURCE_FILES})
set_target_properties(${LINUX_EXE} PROPERTIES COMPILE_OPTIONS "-m32" LINK_FLAGS "-m32")
target_link_libraries(${LINUX_EXE} ${SDL2_LIBRARIES})