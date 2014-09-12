.. _vph2014-index:

================================
VPH 2014 - ABI Software Tutorial
================================

This documentation has been prepared for the session, *"VPH tools from the Auckland Bioengineering Institute"*, presented at the `VPH 2014 <http://www.ntnu.edu/vph2014/>`_ meeting.

This tutorial will demonstrate some of the tools, techniques and best practices developed at the `Auckland Bioenginerring Institute <http://www.abi.auckland.ac.nz>`_ that aid scientists in the development and application of computational models and simulation experiments in their work toward the creation of a virtual physiological human. The :ref:`Auckland Physiome Repository <abi-pmr2-index>` provides a framework for the storage, curation and exchange of data. By using standards suitable to their data, scientists maximise their ability to reuse existing knowledge and enable others to make use of their achievements in novel work. Annotations ensure scientists are able to find existing data and are also able to correctly interpret and apply their own data. These tutorials are designed to help demonstrate and promote practices which will aid attendees in their own work. Attendees are encouraged to raise issues specifically related to their needs with the tutors.

Documentation for the software used in this tutorial is available `online <http://vph2014-abi-tutorial.readthedocs.org/>`_, including the most recent version of `the tutorial itself <http://vph2014-abi-tutorial.readthedocs.org/en/latest/tutorialOverview.html>`_. This tutorial guides the particpant through various common computational modelling scenarios faced by scientists working toward the virtual physiologial human. We use these scenarios to achieve scientific outputs using the covered tools and demonstrating practices we believe will help ensure reproducible and reusable science.

When interacting directly with :term:`Mercurial`, this tutorial demonstrates how to work with the repository using `TortoiseHg <http://tortoisehg.bitbucket.org/>`_, which provides a Windows explorer integrated system for working with Mercurial repositories.

.. note::
   Brief mention of the equivalent command line versions of the TortoiseHg
   actions will also be mentioned, so that these ideas can also be used without
   a graphical client, and on Linux or OS X and similar systems. These will be denoted
   by boxes like this.

This tutorial requires you to have:

* A Mercurial client such as `TortoiseHg <http://tortoisehg.bitbucket.org/>`_ or `Mercurial <http://mercurial.selenic.com/>`_ installed;
* The :ref:`OpenCOR <OpenCOR-downloadLinks>` CellML modelling environment and/or the :ref:`MAP <MAP-install-setup>` workflow tool installed; and
* Possibly a text editor such as `Notepad++ <http://notepad-plus-plus.org/>`_ or `gedit <http://projects.gnome.org/gedit/>`_.

The tutorial makes use of two primary tools, OpenCOR and MAP Client, as well as the model repository. For convenience, documentation for each of these projects has been collated here, corresponding to the versions of the tools used in the tutorial.

Contents:

.. toctree::
   :maxdepth: 1
   :titlesonly:

   tutorialOverview
   PMR2/index
   OpenCOR/index
   MAP/index
   glossary
   todoList

.. toctree::
   :hidden:

   MAP/README.rst
   tutorialMap



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
