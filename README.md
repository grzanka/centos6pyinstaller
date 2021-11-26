# centos6pyinstaller
The aim of this Docker image is to provide a platform able to produce **single-file executables** from **Python** applications that runs **on quite old Linux distributions**.

Main features
 - This docker image can be run on most of modern platform, nowadays also Windows supports Docker
 - In the image pyinstaller python package is installed which is capable of transforming a python code (including many libraries and python interpreter) into single executable with minimum set of dependencies. 
 - We've installed python 3.9.9 (released on Nov. 15, 2021), which means that Python code compatible with **modern 3.9 Python version** can be packaged into single binaries as well. 
 - The single-binaries depends on glibc library. We have choosen ancient Linux distribution CentOS6 which comes with glibc v2.12 (released on 2010.05.03). That means that single binaries produced on this Docker image should run basically on every Linux distribution with glibc v2.12 or newer (in other words, on most distros released **from year 2010 onwards**).

To build the image simply run::

```
docker build .
```

Once the container image is ready, add your python code inside and run inside container `pyinstaller -F mycode.py`