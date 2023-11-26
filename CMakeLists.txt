cmake_minimum_required(VERSION 3.27)
project(hello LANGUAGES CXX)

# 设置C++标准
set(CMAKE_CXX_STANDARD 11)

# 设置输出目录
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/output)

# 设置编译器
set(CMAKE_C_COMPILER gcc)
set(CMAKE_CXX_COMPILER g++)

# 设置编译选项


# 添加头文件目录
include_directories(include)

aux_source_directory(src hello)
aux_source_directory(test hello_test)

# 生成可执行文件
add_executable(hello ${hello} ${hello_test})

# 链接Google Test库
# target_link_libraries(hello gtest)
