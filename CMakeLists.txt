cmake_minimum_required(VERSION 3.30)

project(MyCMakeProject)

add_executable(
    my_cmake_project
    "code/main.cpp"
)

target_compile_features(my_cmake_project PRIVATE cxx_std_23)

set_target_properties(
    my_cmake_project
    PROPERTIES
        UNITY_BUILD true
        CXX_SCAN_FOR_MODULES false # Need to disable scanning for modules since we're using unity build.
)

install(TARGETS my_cmake_project)
