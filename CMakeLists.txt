cmake_minimum_required (VERSION 2.6)
project (FSCK)

set (SOURCES
	main.c
	boot.c
	check.c
	dir.c
	fat.c)

set(CMAKE_C_FLAGS "-lbsd")

include_directories("${PROJECT_SOURCE_DIR}/fsutil")
add_subdirectory("${PROJECT_SOURCE_DIR}/fsutil")

add_executable(FSCK ${SOURCES})
target_link_libraries(FSCK fsutil)