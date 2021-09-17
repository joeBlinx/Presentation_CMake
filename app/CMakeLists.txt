#[[
    This is what we called the CMake top directory
]]
#[[
The CMake top directory should always begin with cmake_minimum_required(VERSION X.YY)
It permit to specifiy that you're project will work with CMake at least X.YY

But beware if you use a more recent version, this line won't stop you to use recent features not supported
by version X.YY.
]]
cmake_minimum_required(VERSION 3.12)
project(micro_tuto)

add_executable(app)
add_subdirectory(static_lib)

target_link_libraries(app PRIVATE Tuto::HelloStatic)
target_sources(app PRIVATE
        src/main.cpp
)