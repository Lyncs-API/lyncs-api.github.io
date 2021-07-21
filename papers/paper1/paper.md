---
title: 'Lyncs-API: Python interfaces for Lattice QCD libraries'
tags:
  - Python
  - Lattice QCD
  - MPI
  - cppyy
  - Dask
authors:
  - name: Simone Bacchio
    orcid: 0000-0002-5532-450X
    affiliation: 1
  - name: Constantia Alexandrou
    affiliation: "1, 2"
  - name: Jacob Finkenrath
    affiliation: 1
  - name: Giannis Koutsou
    affiliation: 1
affiliations:
 - name: Computation-based Science and Technology Research Center, The Cyprus Institute, 20 Kavafi Str., Nicosia 2121, Cyprus
   index: 1
 - name: Department of Physics, University of Cyprus, P.O. Box 20537, 1678 Nicosia, Cyprus
   index: 2
   
date: 13 August 2017
bibliography: paper.bib

---

# Summary

This is the first progress report of the Lyncs-API project, a Python API for Lattice
Quantum Chromodynamics (QCD) applications.
The Lyncs-API plans to support a large number of libraries widely used by the Lattice QCD community.
Common libraries for Lattice QCD are written in C/C++ and use MPI for data-distributed calculations.

In this report we review our approach and experience in interfacing to these libraries.
We use the package `cppyy` [@lavrijsen2016high] for automatically creating Python bindings and
`dask` [@rocklin2015dask] for supporting distributed tasking and data manipulation.

The Python interfaces we present are `lyncs.DDalphaAMG` interface to DDalphaAMG [@],
a multigrid solver library for Wilson and Twisted Mass fermions, `lyncs.quda` interface to QUDA [@],
a GPU-enabled library for Lattice QCD, and `lyncs.tmLQCD` interface to tmLQCD [@],
a legacy code of the Extended Twisted Mass collaboration. We use these first interfaces we have
created as an example of the flexibility our approach aims to, supporting from legacy codes to
fully-fledged community codes.

# Introduction

Lattice Quantum Chromodynamics (QCD) is a technologically driven field that benefits from the fast
evolution of computers and data technologies. It is a fundamental science research that studies
the strong interactions described by QCD, responsible for binding quarks and gluons within nucleons
of atoms.

We are working on the

- Flexibility
- Portability
- Modularity
- User-friendly
-


# Acknowledgements

PRACE-6IP, Grant agreement ID: 823767, Project name: LyNcs. Lyncs is one of 10 applications supported by PRACE-6IP, WP8 "Forward Looking Software Solutions".

# References
