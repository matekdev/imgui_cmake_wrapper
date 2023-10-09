# imgui CMake Wrapper

## History

While trying to setup a new C++ project with imgui using CMake I was confronted with the lack of CMake support for imgui. While cloning the imgui repository and adding the necessary sources and headers to your targets works fine and is simple to do, it feels like unnecessary struggle in the age of CMake FetchContent and CPM. In order to enable CMake support I wrote a simple wrapper configuration for the glfw + opengl3 backend combination. This is a first try at this, and is merely an effort to make my life easier the next time I want to work with imgui.

## Contributions

If you want to support this effort and improve the existing configuration or add support for additional backends you are welcome to create a pull request. 

