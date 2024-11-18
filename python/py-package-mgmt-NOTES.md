
# conda
```
source ~/miniconda3/bin/activate ml_datasci

```

## resources
- ### [Most popular sorfware locences](https://www.tldrlegal.com/)
- ### [available classifiers](https://pypi.org/classifiers/)

## [How to Build a Complete Python Package Step-by-Step](https://www.youtube.com/watch?v=5KEObONUkik)
- ### [example app](https://github.com/ArjanCodes/2023-package)
  - ### [Key INFO](https://github.com/heidless-stillwater/py-package-mgmt/blob/main/2023-package/outline.md)
- ### [Arjan Codes courses](https://www.arjancodes.com/courses/)

## [Packaging Python Projects](https://packaging.python.org/en/latest/tutorials/packaging-projects/)








## setuptools
- **setuptools** is a (now standard) python library that facilitates packaging python projects by enhancing the distutils library.
- Important keywords/parameters of _setuptools_ to be aware of:
  - **wheel (.whl)**: A pre-built (zip) binary file, which is ready to be installed, that contains all the necessary information (code itself and metadata) for python package manager to install the package. 
  - To create one you should run `python setup.py bdist_wheel` within the shell. bdist stands for binary distribution.
  - sdist (.tar.gz) : The source code distribution equivalent to wheel. A tar file (zip) that contains the source code together with the [setup.py](http://setup.py) file, so the user can re-built it. To create a source distribution run `python setup.py sdist`  
- The above two commands can be combined into one, if both distributions are desired. The output will be stored within the _dist_ folder that setuptools will create in the same level with [setup.py](http://setup.py) resides.
- The build folder: Contains all the source code / modules that will be distributed.
- egg-info: A directory placed adjacent to the project's code and resources, that directly contains the project's metadata. Replaced by wheels. (directly from Wikipedia)
  - Python eggs are a way of bundling additional information with a Python project, that allows the project's dependencies to be checked and
    satisfied at runtime, as well as allowing projects to provide [plugins](<https://en.wikipedia.org/wiki/Plug-in_(computing)>) for other projects. (quoting wikipedia)

- 
```
python setup.py bdist_wheel sdist

```

