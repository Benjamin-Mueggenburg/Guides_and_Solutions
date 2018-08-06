## Windows
### - Cannot install Pycocotools
**The Problem** <br>
When trying to install Pycocotools, on Windows 10, through setup.py, an error appears <br>
**Solution** <br>
1. Open CMD (with or without virtual-env)

2. Install `Cython` through `pip install Cython`

3. Install `pycocotools` through `pip install git+https://github.com/philferriere/cocoapi.git#egg=pycocotools^&subdirectory=PythonAPI`

:tada: Congradulations you have install pycocotools! :tada:
