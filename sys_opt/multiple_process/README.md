Multiple Process (C)
======================

This example will demonstrate how to run multiple processes to utilize multiple kernels simultaneously on an FPGA device. Multiple processes can share access to the same device provided each process uses the same xclbin. Processes share access to all device resources but there is no support for exclusive access to resources by any process.

***KEY CONCEPTS:*** Concurrent execution, Multiple HLS kernels, Multiple Process Support

***KEYWORDS:*** PID, fork, XCL_MULTIPROCESS_MODE, multiprocess

##  DESIGN FILES
Application code is located in the src directory. Accelerator binary files will be compiled to the xclbin directory. The xclbin directory is required by the Makefile and its contents will be filled during compilation. A listing of all the files in this example is shown below

```
src/host.cpp
src/krnl_vadd.cpp
src/krnl_vmul.cpp
src/krnl_vsub.cpp
src/multi_krnl.h
```

##  COMMAND LINE ARGUMENTS
Once the environment has been configured, the application can be executed by
```
./host <multi_krnl XCLBIN>
```

##  COMMANDS FOR WINDOWS FLOW
Once the environment has been configured, run the following commands : 
```
cd cmake_build
cmake -G "Visual Studio 15 2017 Win64" -DCMAKE_BUILD_TYPE=Debug -DXILINX_XRT=<set xilinx xrt path> -DOCL_ROOT=<set ocl root path>
cmake --build . --verbose --config Debug --target install

For Example : 
cd cmake_build
cmake -G "Visual Studio 15 2017 Win64" -DCMAKE_BUILD_TYPE=Debug -DXILINX_XRT=C:\Xilinx\XRT -DOCL_ROOT=C:\Xilinx\XRT\ext
cmake --build . --verbose --config Debug --target install
```
