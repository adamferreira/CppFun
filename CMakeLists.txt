cmake_minimum_required(VERSION 3.13)

project(CppFun)

set(CMAKE_CXX_STANDARD_REQUIRED ON)

if(NOT "${CMAKE_CXX_STANDARD}")
  set(CMAKE_CXX_STANDARD 20)
endif()

message("CMAKE_CXX_STANDARD is ${CMAKE_CXX_STANDARD}")

include_directories(include)

if (CMAKE_CXX_STANDARD EQUAL 98)
	add_subdirectory(vanilla)
else()
	add_subdirectory(vanilla)
	if (CMAKE_CXX_STANDARD GREATER_EQUAL 11)
		add_subdirectory(cpp11)
	endif()
	if (CMAKE_CXX_STANDARD GREATER_EQUAL 14)
		add_subdirectory(cpp14)
	endif()
	if (CMAKE_CXX_STANDARD GREATER_EQUAL 17)
		add_subdirectory(cpp17)
	endif()
	if (CMAKE_CXX_STANDARD GREATER_EQUAL 20)
		add_subdirectory(cpp20)
	endif()
	if (CMAKE_CXX_STANDARD GREATER_EQUAL 23)
		add_subdirectory(cpp23)
	endif()
endif()