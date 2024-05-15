cmake_minimum_required(VERSION 3.4...3.18)
project(cmake_example)

# create static library (will create .a file)
add_library(my_math STATIC src/my_math.cpp)

set_target_properties(my_math PROPERTIES POSITION_INDEPENDENT_CODE ON)

# could deploy my_math as C++ library (ship headers and .a file)
# create executable for unit testing
# create separate executable

add_subdirectory(pybind11)
pybind11_add_module(cmake_example src/pybind_wrapper.cpp)

# link the 2 libraries (PRIVATE bc othing downstream needs to see the dependency on my_math)
target_link_libraries(cmake_example PRIVATE my_math)