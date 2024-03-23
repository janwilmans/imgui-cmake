
add_library(imgui_demo STATIC
    imgui_demo.cpp
)
add_library(imgui::demo ALIAS imgui_demo)

find_package(glfw3 3.3 REQUIRED)
find_package(OpenGL REQUIRED)

add_library(imgui_library STATIC
    imgui.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
    # backends/imgui_impl_dx10.cpp
    # backends/imgui_impl_sdlrenderer2.cpp
    # backends/imgui_impl_dx12.cpp
    # backends/imgui_impl_sdlrenderer3.cpp
    # backends/imgui_impl_wgpu.cpp
    # backends/imgui_impl_win32.cpp
    # backends/imgui_impl_dx11.cpp
    # backends/imgui_impl_sdl2.cpp
    backends/imgui_impl_glfw.cpp
    # backends/imgui_impl_opengl2.cpp
    # backends/imgui_impl_dx9.cpp
    # backends/imgui_impl_allegro5.cpp
    # backends/imgui_impl_glut.cpp
    backends/imgui_impl_opengl3.cpp
    # backends/imgui_impl_vulkan.cpp
    # backends/imgui_impl_sdl3.cpp
    # backends/imgui_impl_android.cpp
)
add_library(imgui::imgui ALIAS imgui_library)

target_include_directories(imgui_library PUBLIC .)
target_include_directories(imgui_library PUBLIC backends)

target_link_libraries(imgui_library
   PRIVATE
   glfw
   OpenGL::GL
   ${CMAKE_DL_LIBS}
)

