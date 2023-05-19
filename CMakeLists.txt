cmake_minimum_required(VERSION 3.14)
project(template)

set(CMAKE_EXPORT_COMPILE_COMMANDS "1")
set(CMAKE_CXX20_STANDARD_COMPILE_OPTION "-std=c++20")
set(CMAKE_CXX_STANDARD 20)

add_definitions("-march=native")

# setup platform-independent directories
# include_directories(lib)

# setup platform-specific directories
if (WIN32)
    # ex: find Boost lib on windows
    # set(BOOST_DIR C:/Libraries/boost_1_83_0)
    # include_directories(
    #     "${BOOST_DIR}"
	# )
	# link_directories(
    #     "${BOOST_DIR}/stage/lib"
	# )
endif (WIN32)

if (UNIX)
    # https://cmake.org/cmake/help/latest/module/FindBoost.html
    # find_package(Boost 1.70.0 REQUIRED COMPONENTS fiber)
    # include_directories(
    #     ${Boost_INCLUDE_DIRS}
    # )
endif (UNIX)

add_executable(template
    app/main.cpp)

# setup platform-specific links
if (WIN32)
	#target_link_libraries(main Rpcrt4 Kernel32)
endif (WIN32)
if (UNIX)
	#target_link_libraries(main ${Boost_LIBRARIES}) 
endif (UNIX)

# copy compile_commands.json to the root directory after build so clangd can find it
# clangd won't look in the /build/{config} directory, only in the top-level /build directory
add_custom_command(TARGET template POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy_if_different
        ${CMAKE_BINARY_DIR}/compile_commands.json
        ${CMAKE_CURRENT_LIST_DIR}/build
    )