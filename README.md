# separative_compilation_example
# ref : http://devblogs.nvidia.com/parallelforall/separate-compilation-linking-cuda-device-code/

In source code, __host__ and __device__ keywords indicate nvcc to compile these
routines into both CPU code and device-callable GPU code otherwise completely
unchanged from their CPU-only version.

In Makefile, `-dc` option tells nvcc to generate device code for later linking.
It is worth noting that we have specified –arch=sm_20 before the –dc option,
since not all SM code variants support device linking.

`–x` option tells nvcc to treat the input files as .cu files containing both
CPU and GPU code. By default, nvcc treats .cpp files as CPU-only code. 
