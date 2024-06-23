# VTA: Versatile Tensor Accelerator

The Versatile Tensor Accelerator (VTA) is an open, generic, and customizable deep learning accelerator with a complete TVM-based compiler stack. We designed VTA to expose the most salient and common characteristics of mainstream deep learning accelerators. Together TVM and VTA form an end-to-end hardware-software deep learning system stack that includes hardware design, drivers, a JIT runtime, and an optimizing compiler stack based on TVM.

Try these steps for HLS setup:


1. Create a vitis hls project
* source files:
* vta.cc
* vta.h

* TB files:
* test_lib.cc
* vta_test.cc
* test_lib.h

3. Generate CFLAGS with below cmd (better to run from the dir of your proj file)

* python3 ./tvm/3rdparty/vta-hw/config/vta_config.py --cflags
* set the above CFLAGS in project -> settings.

4. Set below as LINKER FLAGS: (Project Settings --> Simulation --> Link flags)
* "-z stack-size=1073741824" 

 
5. Pick only 2/3 tests in vta_test.cc  (comment the rest)

    * alu_test

    * gemm_test

    * blocked_gemm_test

6. Run C Simulation

For more information Visit https://tvm.apache.org/docs/topic/vta/index.html

