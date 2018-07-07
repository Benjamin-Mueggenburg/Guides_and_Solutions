## Windows
### - Tensorflow - No module named '_pywrap_tensorflow_internal'
**The Problem** <br>
While running `python object_detection/builders/model_builder_test.py` you get the error ` ModuleNotFoundError: No module named '_pywrap_tensorflow_internal'` <br>
**Solution** <br>
Follow this [ https://github.com/tensorflow/tensorflow/issues/17386]( https://github.com/tensorflow/tensorflow/issues/17386) it suggests that this error can occur if the current CPU of the PC lacks AVX instructions. _**A**dvanced **V**ector E**x**tensions_ (AVX) are a set of instructions for doing Single Instruction Multiple Data (SIMD) operations. 

To see whether your PC's CPU supports AVX instructions, look for it here: [https://en.wikipedia.org/wiki/Advanced_Vector_Extensions#CPUs_with_AVX](https://en.wikipedia.org/wiki/Advanced_Vector_Extensions#CPUs_with_AVX). If you cannot find it then there is a high probability that your CPU does not support AVX instructions thus this may be the root of the problem.

Thankfully a user by the name of fo40225 has compiled tensorflow without AVX.

So to fix the problem download the tensorflow wheel without AVX instructions from here:
[ https://github.com/fo40225/tensorflow-windows-wheel/tree/master/1.7.0/py36/CPU/sse2]( https://github.com/fo40225/tensorflow-windows-wheel/tree/master/1.7.0/py36/CPU/sse2) 

Next uninstall tensorflow if you already have it through `pip uninstall tensorflow`

Now install the new tensorflow through `pip install /example/path/to/.whl`. If the path to the .whl that you just download has whitespaces (or spaces) you need to put speech marks ("") around the path so CMD knows that it's only one thing and not multiple.

Tensorflow should be installed!
