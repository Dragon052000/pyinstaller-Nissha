Purpose
----------
The purpose of this fork is to comment out the following section in the Compat.py file so that pyinstaller will not check if pathlib is installed. 
for name in ["enum34", "typing", "pathlib"]:
try:
dist = distribution(name)
except PackageNotFoundError:
continue
remove = "conda remove" if is_conda else f'"{sys.executable}" -m pip uninstall {name}'
raise SystemExit(
f"The '{name}' package is an obsolete backport of a standard library package and is incompatible with "
f"PyInstaller. Please remove this package (located in {dist.locate_file('')}) using\n    {remove}\n"
"then try again."
 )
 Installation
------------

PyInstaller is available on PyPI. You can install it through `pip`:

.. code:: bash

      pip install pyinstaller@git+https://github.com/Dragon052000/pyinstaller-Nissha.git

Usage
-----

Basic usage is very simple, just run it against your main script:

.. code:: bash

      pyinstaller /path/to/yourscript.py
 
 Author
----------
By: Greg Beck, Project Engineer, Nissha USA, Dated 21 Apr 2023  