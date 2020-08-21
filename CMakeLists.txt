cmake_minimum_required(VERSION 3.10)
project(cpack_install_exe_cpp VERSION 0.0.1 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)

add_executable(${PROJECT_NAME} main.cpp)

## Install commands
install(TARGETS ${PROJECT_NAME}
#    RUNTIME DESTINATION bin # to /usr/bin
        RUNTIME DESTINATION "/tmp/cpack-example" # for executables .out or .exe or no-ext
    #    LIBRARY DESTINATION "/usr/lib" # for shared libraries .so or .dll
    #    ARCHIVE DESTINATION lib # for static libraries .a or .lib
    #    DESTINATION "/tmp/cpack-example" # ??
    #    EXPORT MyTargets # ??
    #    INCLUDES DESTINATION include # ??
    )

## Pack commands
SET(CPACK_GENERATOR "DEB") # Create a projectname-version-Linux.deb
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "firstname lastname <email@email.com>") # mandatory

##  Pack Optional information
set(CPACK_DEBIAN_PACKAGE_NAME "cpack_install_example") # no spaces allowed
#set(CPACK_DEBIAN_PACKAGE_VERSION "3.2.1") # numbers only
set(CPACK_DEBIAN_PACKAGE_ARCHITECTURE "amd64") # dpkg --print-architecture
set(CPACK_DEBIAN_PACKAGE_DESCRIPTION "Example of cpack usage in cmake")
set(CPACK_PACKAGE_VENDOR "Vendor name")
set(CPACK_RESOURCE_FILE_LICENSE "${CMAKE_CURRENT_SOURCE_DIR}/LICENSE")
set(CPACK_RESOURCE_FILE_README "${CMAKE_CURRENT_SOURCE_DIR}/README.md")
#set(CPACK_DEBIAN_PACKAGE_DEPENDS "libc6 (>= 2.3.1-6), libgcc1 (>= 1:3.4.2-12)")
#set(CPACK_PACKAGE_VERSION_MAJOR ${PROJECT_VERSION_MAJOR})
#set(CPACK_PACKAGE_VERSION_MINOR ${PROJECT_VERSION_MINOR})
#set(CPACK_PACKAGE_VERSION_PATCH ${PROJECT_VERSION_PATCH})

INCLUDE(CPack)
