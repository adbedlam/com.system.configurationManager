cmake_minimum_required(VERSION 3.28)
project(config_manager)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(PkgConfig REQUIRED)
pkg_check_modules(SDBUS_CPP REQUIRED sdbus-c++)

add_executable(config_manager main.cpp)

target_include_directories(config_manager PRIVATE ${SDBUS_CPP_INCLUDE_DIRS})
target_link_libraries(config_manager PRIVATE ${SDBUS_CPP_LIBRARIES})
target_compile_options(config_manager PRIVATE ${SDBUS_CPP_CFLAGS_OTHER})
