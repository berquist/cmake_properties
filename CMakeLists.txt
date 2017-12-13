cmake_minimum_required(VERSION 3.9)

find_package(Armadillo REQUIRED CONFIG)
find_package(Armadillo REQUIRED)
# message(STATUS "Armadillo_CONFIG: ${Armadillo_CONFIG}")

get_target_property(Armadillo_LINK_LIBRARIES armadillo INTERFACE_LINK_LIBRARIES)
message(STATUS "Armadillo_LINK_LIBRARIES: ${Armadillo_LINK_LIBRARIES}")
message(STATUS "Using Armadillo version ${ARMADILLO_VERSION_STRING}")

# foreach(Armadillo_LINK_LIBRARY ${Armadillo_LINK_LIBRARIES})
#     # message(STATUS "${Armadillo_LINK_LIBRARY}")
#     # Convert /usr/lib/libfoo.so -> foo
# endforeach()

# Inspect all current CMake variables.
# https://stackoverflow.com/a/9328525/3249688
get_cmake_property(_variableNames VARIABLES)
foreach (_variableName ${_variableNames})
    message(STATUS "${_variableName}=${${_variableName}}")
endforeach()
