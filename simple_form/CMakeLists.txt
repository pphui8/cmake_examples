project(Test1)
#设置最小版本支持
cmake_minimum_required(VERSION 3.0)

#添加指定目录下的源文件（.c/.cpp源文件）
aux_source_directory(${CMAKE_CURRENT_LIST_DIR}/src/　　SRC_LIST_SDK )

#添加需要编译的头文件
include_directories(${CMAKE_CURRENT_LIST_DIR}/include/)

add_subdirectory(${CMAKE_CURRENT_LIST_DIR}/src/)

#生成目标文件为可执行文件
add_executable(SDK ${SRC_LIST_ALL})

#链接为最终的可执行文件
target_link_libraries(SDK)