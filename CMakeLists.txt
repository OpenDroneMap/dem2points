project(dem2points)
cmake_minimum_required(VERSION 2.8)

if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE "Release" CACHE STRING
      "Choose the type of build, options are: Debug Release
RelWithDebInfo MinSizeRel."
      FORCE)
endif()

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_SOURCE_DIR})

set (CMAKE_CXX_STANDARD 11)
find_package(GDAL REQUIRED)
include_directories(${GDAL_INCLUDE_DIR})

# Add compiler options.
if (NOT WIN32)
add_definitions(-Wall -Wextra)
endif()

# Add source directory
aux_source_directory("./src" SRC_LIST)
	
# Add exectuteable
add_executable(${PROJECT_NAME} ${SRC_LIST})
	
target_link_libraries(${PROJECT_NAME} ${GDAL_LIBRARY})

install(TARGETS ${PROJECT_NAME} RUNTIME DESTINATION bin)
