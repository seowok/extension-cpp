# C++/CUDA Extensions in PyTorch

An example of writing a C++ extension for PyTorch. See
[here](http://pytorch.org/tutorials/advanced/cpp_extension.html) for the accompanying tutorial.

There are a few "sights" you can metaphorically visit in this repository:

- Inspect the C++ and CUDA extensions in the `cpp/` and `cuda/` folders,
- Build C++ and/or CUDA extensions by going into the `cpp/` or `cuda/` folder and executing `python setup.py install`,
- JIT-compile C++ and/or CUDA extensions by going into the `cpp/` or `cuda/` folder and calling `python jit.py`, which will JIT-compile the extension and load it,
- Benchmark Python vs. C++ vs. CUDA by running `python benchmark.py {py, cpp, cuda} [--cuda]`,
- Run gradient checks on the code by running `python grad_check.py {py, cpp, cuda} [--cuda]`.
- Run output checks on the code by running `python check.py {forward, backward} [--cuda]`.

## Authors

[Peter Goldsborough](https://github.com/goldsborough)



FOR WINDOWS !!!!
================
*set  "VS150COMNTOOLS=C:\Program Files (x86)\Microsoft Visual  Studio\2017\Community\VC\Auxiliary\Build"
*set  CMAKE_GENERATOR=Visual Studio 15 2017 Win64
*set  DISTUTILS_USE_SDK=1
*REM  The following two lines are needed for Python 2.7, but the support for it is  very experimental.
*set  MSSdk=1
*set  FORCE_PY27_BUILD=1
*REM  As for CUDA 8, VS2015 Update 3 is also required to build PyTorch. Use the  following line.
*set  "CUDAHOSTCXX=%VS140COMNTOOLS%\..\..\VC\bin\amd64\cl.exe"
*call "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat" x64 -vcvars_ver=14.11


torch/utils/cpp_extension.py : [line   94]  decode()   >>   decode('latin-1')
-----------------------------------------------------------------------------
torch/utils/cpp_extension.py : [line 223]  '/MD'   >>   '/MT'
-------------------------------------------------------------
lltm_cuda_kernel.cu : [line28] scalar_t 추가  >>  fmax(scalar_t(0.0), z) + fmin(scalar_t(0.0), alpha * (exp(z) - scalar_t(1.0)))
--------------------------------------------------------------------------------------------------------------------------------

python setup.py install
python jit.py
