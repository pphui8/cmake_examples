project(Test4)
include_directories(./add ./sub)

################################
# goto sublib to find cmakelist
################################
add_subdirectory(./add)
add_subdirectory(./sub)

aux_source_directory(./ DIR_SRCS)
add_executable(start ${DIR_SRCS})
target_link_libraries(start myadd mysub)