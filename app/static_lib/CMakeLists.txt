add_library(hello_static)
add_library(Tuto::HelloStatic ALIAS hello_static)

target_include_directories(hello_static
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/inc
    PRIVATE ./inc/static_lib
)
target_sources(hello_static PRIVATE
    src/hello.cpp
    inc/static_lib/hello.hpp
)