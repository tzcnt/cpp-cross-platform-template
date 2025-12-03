cmake_minimum_required(VERSION 3.14)
project(template)

set(CMAKE_EXPORT_COMPILE_COMMANDS "1")
set(CMAKE_CXX20_STANDARD_COMPILE_OPTION "-std=c++20")
set(CMAKE_CXX_STANDARD 20)

# setup platform-independent directories
# include_directories(lib)

# setup platform-specific directories
if(WIN32)
    # ex: find Boost lib on windows
    # set(BOOST_DIR C:/Libraries/boost_1_83_0)
    # include_directories(
    # "${BOOST_DIR}"
    # )
    # link_directories(
    # "${BOOST_DIR}/stage/lib"
    # )
endif(WIN32)

if(UNIX)
    # https://cmake.org/cmake/help/latest/module/FindBoost.html
    # find_package(Boost 1.70.0 REQUIRED COMPONENTS fiber)
    # include_directories(
    # ${Boost_INCLUDE_DIRS}
    # )
endif(UNIX)

# Define any number of programs
add_executable(template
    app/main.cpp)

# setup platform-specific links
if(WIN32)
    # target_link_libraries(main Rpcrt4 Kernel32)
endif(WIN32)

if(UNIX)
    # target_link_libraries(main ${Boost_LIBRARIES})
endif(UNIX)
