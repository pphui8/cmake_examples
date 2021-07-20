# cmake演示

- [单源文件](./single_source_file/)  
- [多源文件](./more_source_file/)  
- [多源文件及多lib文件演示1](./more_lib_src_1/)  
- [多源文件及多lib文件演示2](./more_lib_src_2/)  
- [标准工程文件格式](./standerd_example/)  

### 标准项目cmake内容
```cmake
#使用的cmake版本，必填，根据实际项目而定
cmake_minimum_required(VERSION 3.0)

#工程名称，自定义
project (SDK)
#添加指定目录下的源文件（.c/.cpp源文件）
aux_source_directory(${CMAKE_CURRENT_LIST_DIR}/src/　　SRC_LIST_SDK )
#设置需要编译的源文件
list (APPEND SRC_LIST_ALL　　${SRC_LIST_SDK})

#添加需要编译的头文件
include_directories(${CMAKE_CURRENT_LIST_DIR}/include/)

#设置编译参数
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${LOCAL_W_FLAGS} ${LOCAL_C_FLAGS}")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${LOCAL_W_FLAGS} ${LOCAL_C_FLAGS} -std=c++14 ")

#设置链接的库
link_directories(${CMAKE_CURRENT_LIST_DIR}/lib/)
#设置链接的库
link_libraries(z ssl crypto boost_system boost_program_options boost_filesystem boost_date_time boost_context boost_coroutine boost_chrono boost_log boost_thread boost_log_setup boost_regex boost_atomic pthread )

#生成目标文件为可执行文件
add_executable(SDK ${SRC_LIST_ALL})

#链接为最终的可执行文件
target_link_libraries(SDK)
```
