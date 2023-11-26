cmake_minimum_required(VERSION 3.27)
project(hello LANGUAGES CXX)

# 设置C++标准
set(CMAKE_CXX_STANDARD 11)

# 设置输出目录
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/output)
set(CMAKE_BINARY_DIR ${CMAKE_RUNTIME_OUTPUT_DIRECTORY})
# 将 CMake 生成的文件也放置到 output 目录下
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})

# 设置编译器
set(CMAKE_C_COMPILER gcc)
set(CMAKE_CXX_COMPILER g++)

# 使用 ninja 工具进行构建
set(CMAKE_MAKE_PROGRAM ninja)

# 设置编译选项


# 添加头文件目录
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# 添加子目录
add_subdirectory(src)

# 生成可执行文件
add_executable(main main.cpp)

# 为目标添加头文件搜索路径
target_include_directories(main PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)

# 将动态库链接给可执行文件
target_link_libraries(main hello)


# 链接Google Test库
# target_link_libraries(hello gtest)
