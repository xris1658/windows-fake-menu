cmake_minimum_required(VERSION 3.13)
project(WindowsFakeMenu)

set(CMAKE_CXX_STANDARD 17)

add_executable(WindowsFakeMenu main.cpp)

add_compile_definitions(-DUNICODE)

set_target_properties(WindowsFakeMenu PROPERTIES
                      WIN32_EXECUTABLE TRUE
)

target_link_options(WindowsFakeMenu PRIVATE "/MANIFESTDEPENDENCY:type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' publicKeyToken='6595b64144ccf1df' language='*' processorArchitecture='*'")

target_link_libraries(WindowsFakeMenu PRIVATE Uxtheme dwmapi)