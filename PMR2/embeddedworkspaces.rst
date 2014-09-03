.. _embeddedworkspaces:

==================================
Embedded workspaces and their uses
==================================

.. sectionauthor:: David Nickerson

.. todo::
   This section needs more work.

:term:`Workspaces` in PMR are currently implemented as :term:`Mercurial`
repositories. One Mercurial feature that is quite useful in the context
of the Auckland Physiome Repository is `nested repositories
<http://mercurial.selenic.com/wiki/Subrepository>`_. Using the more
general :term:`PMR2` concepts, we term such nesting as :term:`embedded
workspaces`.

Embedded workspaces:

- are intended to manage the separation of modules which are integrated
  to create a model;
- facilitate the sharing and reuse of model components independently
  from the source model;
- enable the development of the modules to proceed independently, thus
  the version of the workspaces embedded is also tracked; and
- allow authors to make use of relative URIs when linking between data
  resources providing a file system agnostic method to describe complex
  module relationships in a portable manner.

Workspaces can be embedded at a specific revision or set to track the
most recent revision of the source workspace. Changes made to the source
workspace will not affect any embedding workspace until the author
explicitly chooses to update the embedded workspace. This provides the
author with the opportunity to review the changesets and make an
informed decision regarding alterations to embedded revisions. Any
alterations in the specific revision of an embedded workspace is data
captured in a changeset in the embedding workspace – thus providing a
clear provenance record of the entire dataset in the workspace.

Uses
====

Best practice
=============

See also the `recommendations
<http://mercurial.selenic.com/wiki/Subrepository#Recommendations>`_ from
the Mercurial project.
