# Test Package

This project is a minimum viable package to understand and test how to build a local package and import into a project.

Used in StackOverflow post [here](https://stackoverflow.com/questions/66805833/unable-to-use-locally-built-python-package-in-development-mode)

Wasn't able to build and use package locally. These issues have now been resolved.

Intended result:

```python
python3
>>> import mypackage
>>> mypackage.add2(2)
4
```

Error received:
```python
>>> import mypackage
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'mypackage'
```

## Steps to reproduce:

In the project root, run the following commands:

Install build command
``` bash
python3 -m pip install --upgrade build
```
Build package, this will generate the `build`,`dist` directories and `egg` file 
``` bash
python3 -m build
```
Install package in development mode
``` bash
pip3 install -e .
```

## Additional Info

* Using pycharm with a virtual env

```python
pip3 list

Package       Version     Location
------------- ----------- ----------------------------------------------------
build         0.3.1.post1
mypackage     0.1.0       <HOME_PATH>/dev/testPackage/src/mypackage
mypackagetest 0.1.0
packaging     20.9
pep517        0.10.0
pip           21.0.1
pkg-resources 0.0.0
pyparsing     2.4.7
setuptools    54.2.0
toml          0.10.2


```