getting started on debian 11:

the DemoApplication uses to 'example_glfw_opengl3' code, but in the root CMakeLists.txt you can just pick another example.

$ sudo apt install libglfw3-dev libglfw3 xorg-dev
$ cmake -B build -G Ninja .
$ ninja -C build
