cmake_minimum_required (VERSION 3.1)
message(STATUS ${CMAKE_INSTALL_PREFIX})

project (cperiphery)

message(warning ${PROJECT_VERSION})

set(PROJECT_VERSION 0.0.1)

file (GLOB CPERIPHERY_SOURCES ${PROJECT_SOURCE_DIR}/src/*.c)
file (GLOB CPERIPHERY_INCLUDES ${PROJECT_SOURCE_DIR}/src/*.h)

message(WARNING ${CPERIPHERY_SOURCES})

include_directories (${PROJECT_SOURCE_DIR})

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu99 -pedantic -Wall -Wextra -Wno-unused-parameter -Wno-pointer-to-int-cast -fPIC")
add_library (cperiphery SHARED ${CPERIPHERY_SOURCES})

install(TARGETS cperiphery
    LIBRARY DESTINATION lib)

install(FILES ${CPERIPHERY_INCLUDES}
	 DESTINATION include)