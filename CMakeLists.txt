cmake_minimum_required(VERSION 3.5)
project(lab06)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(formatter_lib)
add_subdirectory(formatter_ex_lib)
add_subdirectory(solver_lib)

add_subdirectory(hello_world_application)
add_subdirectory(solver_application)

set(CPACK_PACKAGE_NAME "solver")
set(CPACK_PACKAGE_VERSION "1.0.0")
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "Quadratic equation solver")
set(CPACK_PACKAGE_VENDOR "from1k")
set(CPACK_PACKAGE_CONTACT "your.email@example.com")

set(CPACK_DEBIAN_PACKAGE_ARCHITECTURE "amd64")
set(CPACK_RPM_PACKAGE_ARCHITECTURE "x86_64")

set(CPACK_DMG_VOLUME_NAME "Solver")
set(CPACK_DMG_FORMAT "UDBZ")

set(CPACK_WIX_UPGRADE_GUID "601D770E-47DF-46A3-B916-A58C3841CFC4")

if(CMAKE_SYSTEM_NAME STREQUAL "Linux")
    set(CPACK_GENERATOR "TGZ;ZIP;DEB;RPM")
elseif(CMAKE_SYSTEM_NAME STREQUAL "Darwin")
    set(CPACK_GENERATOR "TGZ;ZIP;DragNDrop")
elseif(CMAKE_SYSTEM_NAME STREQUAL "Windows")
    set(CPACK_GENERATOR "TGZ;ZIP;WIX")
else()
    set(CPACK_GENERATOR "TGZ;ZIP")
endif()

include(CPack)
