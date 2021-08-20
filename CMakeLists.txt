cmake_minimum_required(VERSION 3.0)
project(re_samp_query_fake LANGUAGES CXX)

aux_source_directory(${CMAKE_CURRENT_SOURCE_DIR}/src ${PROJECT_NAME}_LIST)

add_executable(${PROJECT_NAME} ${${PROJECT_NAME}_LIST})

set_target_properties(${PROJECT_NAME} PROPERTIES
	CXX_STANDART 14
	CXX_STANDART_REQUIRED YES
	CXX_EXTENSIONS NO
)

if(WIN32)
	target_link_libraries(${PROJECT_NAME} ws2_32)
endif()
target_sources(${PROJECT_NAME} PRIVATE)
