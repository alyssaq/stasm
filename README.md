# stasm
Python wrapper of Stasm for finding features in faces.

This has been tested with Python 3.6.5, 3.7 and OpenCV 3.4.1, 4.0.1.

To use:
`$ pip install stasm`

## Description
[Stasm](http://www.milbo.users.sonic.net/stasm/) is a C++ software library for finding features in faces. PyStasm is a library wrapper with simplified Pythonic syntax using the Python C API built on top of [OpenCV](http://opencv.org/) and [NumPy](http://www.numpy.org/). For example, to get a list of facial landmarks from an image:
```python
import cv2, stasm
img = cv2.imread(imgpath, cv2.IMREAD_GRAYSCALE)
landmarks = stasm.search_single(img)
```
A full Python version of the minimal Stasm C++ [example](http://www.milbo.users.sonic.net/stasm/minimal.html) is located in the [documentation](http://pythonhosted.org/PyStasm).

## Requirements
* numpy >= 1.10
* [OpenCV](http://opencv.org/) >= 3.0

## Installation
The recommended way to install stasm is through [PyPI](https://pypi.python.org/pypi/stasm):
```
$ pip install stasm
```
To build from source, make sure you have the OpenCV headers and libraries in your include/library paths and then run:
```
$ python setup.py install
```

## Common errors
`ImportError: libopencv_core.so.3.4: cannot open shared object file: No such file or directory`.   
Run: `export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib`

## Documentation
For information specific to this wrapper, take a look at the PyStasm [API reference](http://pythonhosted.org/PyStasm). For further information about Stasm consult the [user manual](http://www.milbo.org/stasm-files/stasm4.pdf). To build the PyStasm docs:
```
$ pip install Sphinx
$ python setup.py build_ext --inplace
$ cd doc
$ make html
```

## License
Both this software and Stephen Milborrow's original Stasm library are subject to the terms of the BSD-style Stasm License Agreement, available in `LICENSE.txt`.
