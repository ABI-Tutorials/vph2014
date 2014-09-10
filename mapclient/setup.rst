.. _mapclient-setup:

=================================
Setting Up Pre-requisite Software
=================================

MAP Client is dependent on a number of software packages that must be installed before the application can be run.  Some of the plugins that MAP Client makes use of have their own dependencies that must also be installed before the plugins can be used.  Here we outline the required dependencies and some notes on installation.

Dependencies
------------

Much of what is covered here is relevant for windows users only as OS X and GNU/Linux based operating systems already have the required dependencies for MAP Client.  Also GNU/Linux machines have package managers which facilitate the installation of missing dependencies.  It is left as an exercise for the user to install dependencies for operating systems that make use of a package manager.

List of Dependencies
^^^^^^^^^^^^^^^^^^^^

* Python - version 2.7.X is preferred, but version 3.X.Y should also work.
* PySide - Python bindings for the Qt libraries.
* pmr2.client - Python package for using webservices on PMR
* pmr2.wfctrl - Python package for accessing workspaces on PMR
* rdflib - Python package for working with RDF.

Other Dependencies
^^^^^^^^^^^^^^^^^^

As MAP Client is focused on scientific processes the Numpy Python package is quite often used.  It is not required by MAP Client itself but it is used by a number of plugins that essentially make it a requirement.

* Numpy - Python package for numerical algorithms
* Zinc - OpenCMISS-Zinc visualisation library
* PyZinc - Python bindings for the OpenCMISS-Zinc library

