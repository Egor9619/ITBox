cmake_minimum_required(VERSION 3.8)

project("ITBox")

set(INCLUDE_DIR ${CMAKE_SOURCE_DIR}/include)
add_subdirectory(${CMAKE_SOURCE_DIR}/src/nlohmann_json)

add_executable("ITBox"
	ITBox.cpp
	ConvertJSON.cpp

	${INCLUDE_DIR}/ITBox.h
	${INCLUDE_DIR}/ConvertJSON.h
 )

target_link_libraries("ITBox" PRIVATE nlohmann_json::nlohmann_json)
target_include_directories("ITBox" PUBLIC ${INCLUDE_DIR})