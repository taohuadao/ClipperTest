cmake_minimum_required(VERSION 3.25)
project(ClipperTest)

set(CMAKE_CXX_STANDARD 17)

find_package(PkgConfig REQUIRED)
pkg_check_modules(Clipper2 REQUIRED IMPORTED_TARGET Clipper2)
find_package(unofficial-nuklear CONFIG REQUIRED)
find_package(nanovg CONFIG REQUIRED)
find_package(GLEW REQUIRED)
find_package(glfw3 CONFIG REQUIRED)




add_executable(ClipperTest main.cpp)

target_link_libraries(ClipperTest PRIVATE nuklear)
target_link_libraries(ClipperTest PRIVATE PkgConfig::Clipper2)
target_link_libraries(ClipperTest PRIVATE nanovg::nanovg)
target_link_libraries(ClipperTest PRIVATE GLEW::GLEW)
target_link_libraries(ClipperTest PRIVATE glfw)