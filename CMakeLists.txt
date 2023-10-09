cmake_minimum_required(VERSION 3.14)

project(imgui_cmake_wrapper)

set(GLFW_DIR ${PROJECT_SOURCE_DIR}/glfw)
add_subdirectory(${GLFW_DIR})

set(IMGUI_DIR ${PROJECT_SOURCE_DIR}/imgui)

add_library(imgui_cmake_wrapper STATIC)

target_sources(imgui_cmake_wrapper PRIVATE 
                                ${IMGUI_DIR}/imgui.cpp
                                ${IMGUI_DIR}/imgui_draw.cpp
                                ${IMGUI_DIR}/imgui_demo.cpp
                                ${IMGUI_DIR}/imgui_tables.cpp
                                ${IMGUI_DIR}/imgui_widgets.cpp
                                ${IMGUI_DIR}/backends/imgui_impl_opengl3.cpp
                                ${IMGUI_DIR}/backends/imgui_impl_glfw.cpp)

target_include_directories(imgui_cmake_wrapper PUBLIC
                                ${IMGUI_DIR}
                                ${IMGUI_DIR}/backends)   

find_package(OpenGL REQUIRED)
                                
target_link_libraries(imgui_cmake_wrapper PUBLIC glfw ${OPENGL_LIBRARIES})

add_executable(imgui_cmake_wrapper_example ${IMGUI_DIR}/examples/example_glfw_opengl3/main.cpp)
target_link_libraries(imgui_cmake_wrapper_example PUBLIC imgui_cmake_wrapper)