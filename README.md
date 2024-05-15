# Pybind11-Testing

## Build

```
mkdir build
cd build
cmake ..
```

creates the 2 targets (`cmake_example` or `.a` file for `my_math`) that we can subsequently build using `make`, e.g.
```
make cmake_example
```

## Create wheel using `setup.py` and install package

```
python3 setup.py bdist_wheel
```
generates the `.whl` file in the `dist` directory which can now be installed using *pip*
```
cd ..
python3 -m venv .venv
./.venv/bin/pip install dist/WHL_FILE
```
Check that it has been installed to the `site-packages` directory of your virtual environment's Python (here: `python3.10`) 
```
ls .venv/lib/python3.10/site-packages/
```
## Testing

Start a Python shell using `./.venv/bin/python` and try importing and using the functions by entering:
```
import cmake_example
cmake_example.add(4,5)
cmake_example.subtract(4,5)
```