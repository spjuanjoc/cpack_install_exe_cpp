# cpack with cmake

Create a package.deb for a C++ executable

# Steps

1. Generate cmake files

    ````
    mkdir build
    cd build
    cmake ..
    ````

2. Build

    `cmake --build .`

3. Create a deb package named `cpack_install_exe_cpp-0.0.1-Linux`

    `cpack`

4. See package details

    `dpkg-deb -c cpack_install_exe_cpp-0.0.1-Linux.deb`

5. Install

     `sudo dpkg -i cpack_install_exe_cpp-0.0.1-Linux.deb` 

6. Verify installation

    `dpkg -l cpack_install_example`

7. Run

    `/tmp/cpack-example/cpack_install_exe_cpp`
Should print `Hello world!`

8.  Uninstall

     `sudo dpkg -r cpack_install_example`
