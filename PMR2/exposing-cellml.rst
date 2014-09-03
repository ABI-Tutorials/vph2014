.. _exposing-cellml:

=========================
Creating CellML exposures
=========================

.. sectionauthor:: Dougal Cowan

CellML models in the Auckland Physiome Repository are presented through
*exposures*. An :term:`exposure` is a view of a particular revision of a
workspace, and is quite flexible in terms of what it can present. A
workspace may contain one or more models, and any number of models may
be presented in a single exposure. Exposures generally take the form of
some documentation about the model(s), a range of ways of looking at the
model(s) or their metadata, and links to download the model(s).

The example below shows the main exposure page for the Bondarenko *et
al.* 2004 workspace. This workspace contains two models, which can be
viewed via the *Navigation* pane on the right hand side of the page.

.. figure:: images/exposureeg1.png
   :align: center

   **Example of an exposure page**

If you click on one of the model navigation links, it will take you to
the page for that particular model. Exposures most often present a
single model, although they can present any number of models, each with
its own documentation and views.

.. figure:: images/exposureeg2.png
   :align: center

   **Example of a model exposure page**

Most of the CellML exposures in the repository are currently of this
type, with a main documentation page containing navigation links to the
model or models themselves.

The model pages have links that enable the user to do things like view
the model equations, look at the citation information, or run the model
as an interactive session using the OpenCell application. These links
are found in the pane titled *Views available* on the right hand side of
the page.

This tutorial contains instructions on how to create one of these
standard CellML exposures, as well as information about how to create
other alternative types of exposure.

Creating standard CellML exposures
==================================

In this example I will use a :term:`fork` of the the Beeler Reuter 1977
workspace. Creating a *fork* of a workspace creates a *clone* of that
workspace that you own, and can push changes to. You can *fork* any
publicly available workspace in the AUckland Physiome Repository. For
more information on this feature, refer to the information on features
or collaboration, or see the :ref:`relevant section of the tutorial
<tut1forkingaworkspace>`.

At this point you are recommended to submit the workspace for
publication, using the *state:* menu at the top right of the workspace
view page.  This is especially important if you decide to make an
exposure public, as having a private workspace for a public exposure
will impede access of linked data, such as images for the introduction
to that particular exposure.

.. figure:: images/submitworkspaceforpublication.png
   :align: center

   **The state menu is used to submit objects such as workspaces for
   publication. Submitted items will be reviewed by site administrators
   and then published.**

.. _createExposureChooseRevision:

Choose the revision to expose
-----------------------------

As an exposure is created to present a particular revision of a
workspace, the first thing to do is to navigate to that revision. To do
this, first find the workspace - if this is your own workspace, you can
click on the *My Workspaces* button in the navigation bar of the
repository and find the workspace of interest in the listing displayed.
After navigating to your workspace, click on the *history* button in the
menu bar.

.. figure:: images/workspacehistory.png
   :align: center

   **The revision history of a fork of the Beeler Reuter 1977
   workspace**

Now you can select the revision of the workspace you wish to expose by
clicking on the *manifest* of that revision. Usually you will want to
expose the latest revision, which appears at the top of the list.

After selecting the revision you wish to expose, click on the *workspace
actions* menu at the far right end of the menu bar and select *create
exposure*.

.. figure:: images/revisioncreateexposure.png
   :align: center

   **Selecting the manifest of the revision to expose**

.. _buildingTheExposure:

Building the exposure
---------------------

Selecting the *create exposure* option in the menu bar will bring you to
the first page of the exposure *wizard*. This web interface allows you
to select the model files, documentation files, and settings that will
be used to create the exposure.

The initial page of the exposure creation wizard allows you to select
the main documentation file and the first model file. Select the HTML
annotator option and the HTML documentation file for the workspace in
the *Exposure main view* section. For the *New Exposure File Entry*
section, choose the CellML file you wish to expose, and select CellML as
the file type.

.. figure:: images/wizard1.png
   :align: center

   **Selecting the main documentation and the first CellML model file**

.. note:: Documentation should be written in HTML format.  
  Some previous users of the CellML repository may be familiar with the
  tmpdoc style documentation, which has be deprecated. For an example of
  what a fairly standard HTML documentation file might look like, take a
  look at the `documentation for the Beeler Reuter 1977 model
  <http://models.cellml.org/workspace/beeler_reuter_1977/file/fdd29a005ffcf9a72d7ef2479cafb864ea1e887a/beeler_reuter_1977_documentation.html>`_.

Once you have selected the documentation and model files and their
types, click on the *Add* button. This will take you to the next step of
the wizard, where you can select various options for the model you have
chosen to expose, and will allow you to add further model files to the
exposure if desired.

.. figure:: images/wizard2.png
   :align: center

   Note that if your workspace is not publicly accessible, there will
   be an informative note for this which you can safely ignore as there
   are no process within the generation of the exposure that must
   require a publicly accessible workspace.

The wizard shows a *subgroup* for each CellML file to be included in the
exposure.  For each CellML file, select the following options:

- Documentation
   - Documentation file - select the HTML file created to document the
     model
   - View generator - select HTML annotator option
- Basic Model Curation
   - Curation flags - CellML model repository curators may select flags
     according to the status of the model
- License and Citation
   - File/Citation format - select CellML RDF metadata to automatically
     generate a citation page using the model RDF
   - License - select Creative Commons Attributions 3.0 Unported, in the
     cases where the above option is unsuitable.
- Source Viewer
   - Language Type - select xml
- OpenCell Session Link
   - Session File - select the session.xml if it has been created

.. figure:: images/wizard3.png
   :align: center

   **Selecting options for the model file subgroup**

After selecting the subgroup options, you need to select the *Update*
button to apply the chosen options for the exposure builder, as this is
an independent subform to the main form.  The options you selected will
be ignored if this *Update* button is not selected, and the options will
be replaced by the default options when you click *Build* before this
was done.

For exposures where you wish to expose multiple models, click on the
*Add file* button at this stage to create another subgroup. You can then
use this to set up all the same options listed above for the additional
model file. Remember to click *Update* when you have completed selecting
the options for each subgroup before adding another subgroup.

After setting all the options for the models you wish to expose, click
on the *Build* button. The repository software will then create the
exposure pages and display the main page of the exposure.

.. _submitting_exposure:

Making your work publicly accessible
------------------------------------

In order to make the exposure visible and searchable, you will need to
publish it.  You can choose to submit your exposure for review, so that
the repository administrators or curators will know to publish it for
you.  Naturally, if you have sufficient privileges you can publish it
directly.

.. figure:: images/exposurepublish.png
   :align: center

   **Publish your exposure to make it visible to others.**

Other types of exposure
=======================

Because the exposure builder uses HTML documentation, it is possible to
create customized types of exposure that differ from the standard type
shown above. For example, you might want to create an exposure that
simply documents and provides links to models in a workspace that are
encoded in languages other than CellML. You can also use the HTML
documentation to provide tutorials or other documents, with resources
stored in the workspace and linked to from the HTML.

**Examples of other exposure types:**

- `Andre's Hodgkin & Huxley CellML tutorial
  <http://models.cellml.org/e/e1>`_
- `Testing nested SED-ML proposals with CellML
  <http://models.cellml.org/e/c2>`_
- `Aslanidi et al. cardiac models encoded in C
  <http://models.cellml.org/e/ca>`_

Making an exposure using "rollover"
===================================

As explained earlier, an :term:`exposure` aims to bring a particular
revision to the attention of users who are browsing and searching the
repository.

"Rolling over" an exposure is the method used when a workspace already
has an existing exposure, and the updates to the workspace have not
fundamentally changed the structure of the workspace.  This means that
all the information used in making the previous exposure is still valid
for making a new exposure of a more recent revision of the workspace.
Strictly speaking, an exposure can be rolled over to an older revision
as well, but this is not the usual usage.

.. note::
   A forked workspace contains all of the revision history of the
   workspace it was created from, but has no linkages to any of the
   exposures that existed for the original workspace.  However, you may
   navigate to the history of the original workspace and select any
   exposure, then select the wizard tab to the link to its exported
   structure, from which the exposure can be migrated over.  Please
   see :ref:`the section on migrating exposure
   <exposurewizardimportexport>` for more details.

From the view page of your workspace, select "exposure rollover".

.. figure:: images/tut1-rolloverbutton.png
   :align: center

The exposure rollover button takes you to a list of revisions of the
workspace, with existing exposures on the right hand side, and revision
ids on the left. Each revision id has a radio button, used to select the
revision you wish to create a new rolled over exposure for. Each
existing exposure also has a radio button, used to select the exposure
you wish to base your new one on. The most common use case is to select
the latest exposure and the latest revision, and then click the
*Migrate* button at the bottom of the list.

.. figure:: images/tut1-rolloverlist.png
   :align: center

The new exposure will be created and displayed. When a new exposure is
created, it is initially put in the *private* state. This means that
only the user who created it or other users with appropriate permissions
can see it, and it will not appear in search results or model listings.
In order to publish the exposure, you will need to select :ref:`submit
for publication <submitting_exposure>` from the
*state* menu.

The state will change to "pending review". The administrator or curators
of the repository will then review and publish the exposure, as well as
expiring the old exposure.
