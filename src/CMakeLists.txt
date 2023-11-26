# 添加源文件
file(GLOB SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/*.cpp)

# 生成动态库
add_library(hello SHARED ${SOURCES})
