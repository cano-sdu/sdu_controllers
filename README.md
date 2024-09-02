<p>
</p>
<div align="center">
    <img width=35% src="doc/_static/sdu_controllers-logo-graph.png">
</div>
<div align="center">
<p>
</p>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/SDU-Robotics/sdu_controllers/ci.yml?branch=main)](https://github.com/SDU-Robotics/sdu_controllers/actions/workflows/ci.yml)
[![PyPI Release](https://img.shields.io/pypi/v/sdu_controllers.svg)](https://pypi.org/project/sdu_controllers)
[![Documentation Status](https://readthedocs.org/projects/sdu_controllers/badge/)](https://sdu-controllers.readthedocs.io/)
</div>

# sdu_controllers

A C++ library containing robot controllers developed at University of Southern Denmark (SDU).

## Prerequisites

Building sdu_controllers requires the following software installed:

* A C++20-compliant compiler
* CMake `>= 3.9`
* Eigen3 `>= 3.3` for linear algebra.
* Doxygen (optional, documentation building is skipped if missing)
* Python `>= 3.8` for building Python bindings

## Building sdu_controllers

The following sequence of commands builds sdu_controllers.
It assumes that your current working directory is the top-level directory
of the freshly cloned repository:

```
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
cmake --build .
```

The build process can be customized with the following CMake variables,
which can be set by adding `-D<var>={ON, OFF}` to the `cmake` call:

* `BUILD_TESTING`: Enable building of the test suite (default: `ON`)
* `BUILD_DOCS`: Enable building the documentation (default: `ON`)
* `BUILD_PYTHON`: Enable building the Python bindings (default: `ON`)


If you wish to build and install the project as a Python project without
having access to C++ build artifacts like libraries and executables, you
can do so using `pip` from the root directory:

```
python -m pip install .
```

## Testing sdu_controllers

When built according to the above explanation (with `-DBUILD_TESTING=ON`),
the C++ test suite of `sdu_controllers` can be run using
`ctest` from the build directory:

```
cd build
ctest
```

The Python test suite can be run by first `pip`-installing the Python package
and then running `pytest` from the top-level directory:

```
python -m pip install .
pytest
```

## Documentation

sdu_controllers provides a Sphinx-based documentation, that can
be browsed [online at readthedocs.org](https://sdu-controllers.readthedocs.io).
To build it locally, first ensure the requirements are installed by running this command from the top-level source directory:

```
pip install -r doc/requirements.txt
```

Then build the sphinx documentation from the top-level build directory:

```
cmake --build . --target sphinx-doc
```

The web documentation can then be browsed by opening `doc/sphinx/index.html` in your browser.
