## Windows
### - Tensorflow - No module named '_pywrap_tensorflow_internal'
**The Problem** <br>
While running `python object_detection/builders/model_builder_test.py` you get the error `
ModuleNotFoundError: No module named 'nets'` 
**The Solution** <br>
You must add models/research and models/research/slim to PYTHONPATH, which can be found in your environment variables. If using an virtualenv you must edit activate.bat with SET PYTHONPATH=%PYTHONPATH%;C:/path/to/models/research;C:/path/to/models/research/slim
