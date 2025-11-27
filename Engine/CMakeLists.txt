cmake_minimum_required(VERSION 3.16)
project(Engine)

set(CMAKE_CXX_STANDARD 17)

# ---- Add GLFW ----
add_subdirectory(external/glfw)

# ---- Include directories ----
include_directories(
    include
    external/glfw/include
    external/glad/include
    external/glm
)

# ---- Source files ----
set(SOURCES
    src/main.cpp
    external/glad/src/glad.c
)

add_executable(Engine ${SOURCES})

# ---- Link libraries ----
target_link_libraries(Engine
    glfw
    ${CMAKE_DL_LIBS}
)
