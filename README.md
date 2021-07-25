# Lyncs-API
## A Python API for Lattice QCD applications

Lyncs is a Python API for Lattice QCD, currently under development.
Lyncs aims to bring several popular libraries for Lattice QCD
under a common framework. Lyncs interfaces with libraries for
GPUs and CPUs in a way that can accommodate additional computing
architectures as these arise, achieving the best performance for
the calculations while maintaining the same high-level workflow. 

Lyncs distributes calculations using [mpi4py] and [Dask], with bindings to the
libraries performed automatically via [cppyy]. Multiple distributed
tasks can be executed in parallel and different computing units
can be used at the same time to fully exploit the machine allocation.
While Lyncs is designed to quite generally allow linking to multiple
libraries, we focus on a set of targeted packages that include
[c-lime], [DDalphaAMG], [tmLQCD] and [quda]. Any contribution to link
other libraries is very welcome!

[mpi4py]: https://mpi4py.readthedocs.io/en/stable/
[Dask]: https://dask.org/
[cppyy]: https://cppyy.readthedocs.io/
[c-lime]: https://github.com/usqcd-software/c-lime
[DDalphaAMG]:  https://github.com/sbacchio/DDalphaAMG
[tmLQCD]:  https://github.com/etmc/tmLQCD
[quda]:  https://github.com/lattice/quda

### The Lyncs ecosystem

The Lyncs-API is a top-level framework meant to be user-friendly,
flexible, modular and extendable. Under the hood, the project is
divided in many Python (sub-)modules that serve for a specific or
generic purpose. These modules are collected in the [Lyncs-API]
organization and they are shortly described in [List of Lyncs sub-modules].


#### List of Lyncs sub-modules

The modules part of lyncs are the following.

##### Generic purpose

- [lyncs.setuptools](https://github.com/Lyncs-API/lyncs.setuptools):
  utils for automatically deducing the setup arguments and for compiling
  libraries via CMake.

- [lyncs.utils](https://github.com/Lyncs-API/lyncs.utils):
  collection of generic-purpose and stand-alone functions.

- [lyncs.cppyy](https://github.com/Lyncs-API/lyncs.cppyy):
  utils for binding and using C++ libraries using cppyy.

- [lyncs.mpi](https://github.com/Lyncs-API/lyncs.mpi):
  utils for interfacing to MPI libraries using mpi4py and dask.

- [lyncs.io](https://github.com/Lyncs-API/lyncs.io):
  IO functions (`load` and `save`) that support various formats
  and also parallel IO via MPI and Dask.

##### Interfaces to Lattice QCD libraries

- [lyncs.clime](https://github.com/Lyncs-API/lyncs.clime):
  a Python interface to [c-lime].

- [lyncs.DDalphaAMG](https://github.com/Lyncs-API/lyncs.DDalphaAMG):
  a Python interface to [DDalphaAMG].

- [lyncs.tmLQCD](https://github.com/Lyncs-API/lyncs.tmLQCD):
  a Python interface to [tmLQCD].

- [lyncs.quda](https://github.com/Lyncs-API/lyncs.quda):
  a Python interface to [quda].

##### Usage

These modules can be either installed as part of Lyncs,
`pip install lyncs[NAME]`
or independently (suggested for now),
`pip install lyncs_NAME`.

In the first case they can be imported with
`from lyncs import NAME`
or, in both cases, with
`import lyncs_NAME as NAME`.

### Contributing

Lyncs is an open community effort for developing Lattice QCD
applications in Python. We seek for contributions under many
aspect: linking to libraries, expanding the features of the API
and writing of documentation and educational-oriented notebooks.

If you want to contribute, please read the [Developer guide].

For any news or being informed about planned events,
please consider registering to our mailing list.

https://groups.google.com/g/lyncs-api

#### Developer guide

When contributing to a package, clone the source from [github](https://github.com/Lyncs-API/)
and install the package in development mode:

```
pip install -e .[all]
```

Now you can run the test-suite for checking the correctness of the installation:

```
pytest -v
```

If everything goes well, you should see all the tests passed and obtain a coverage report.

A main implementation requirement is a **high code-coverage**.
If you are going to implement something new, please, also add the respective
test files or functions in the `test/` directory.

Another implementation requirement is to **format the code** via [black](https://github.com/ambv/black)
and to use [pylint](https://github.com/PyCQA/pylint) for improving the code standards.

These packages can be installed via pip:

```
pip install black lyncs_setuptools[pylint]
```

Before any commit, run black from the source directory:

```
black .
```

When you are done with the implementation, try to resolve as many comments/warnings/errors
as possible brought up by `pylint`:

```
lyncs_pylint .
```


### Funding

- PRACE-6IP, Grant agreement ID: 823767, Project name: LyNcs.
  Lyncs is one of 10 applications supported by PRACE-6IP, WP8
  "Forward Looking Software Solutions".
