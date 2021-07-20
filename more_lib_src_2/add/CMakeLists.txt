aux_source_directory(./ DIR_LIB_SRCS)

###############################
# 生成静态库
###############################
add_library(myadd STATIC ${DIR_LIB_SRCS})