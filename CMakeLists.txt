cmake_minimum_required(VERSION 2.8)

set(CMAKE_MODULE_PATH
  ${CMAKE_MODULE_PATH}
  "${CMAKE_SOURCE_DIR}/cmake/modules"
)

find_package(LibClang REQUIRED)

add_definitions(${LibClang_DEFINITIONS})

include_directories(
  ${LibClang_INCLUDE_DIRS}
)

add_executable(find-class-decls FindClassDecls.cpp)
target_link_libraries(find-class-decls
  ${LibClang_LIBRARIES}
)
