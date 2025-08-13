#指定cmake最低版本
cmake_minimum_required(VERSION 3.20.0)

#指定项目名称
project(project_car)

# 指定C++标准
set(CMAKE_CXX_STANDARD 17)

# 指定头文件路径
include_directories(${PROJECT_SOURCE_DIR}/include)

# 指定输出路径
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)

# 搜索源文件
aux_source_directory(${PROJECT_SOURCE_DIR}/src SRC_LIST)

# 生成可执行文件
add_executable(project_car ${SRC_LIST})

# 生成库文件
# add_library(myLib STATIC ${SRC_LIST})

target_link_libraries(project_car libeasyx.a)