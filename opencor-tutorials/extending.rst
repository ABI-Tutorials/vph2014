.. _tutorialOpenCOR-newWork:

In the preceeding tutorials, you have learnt how to create a new piece of work from scratch using the respository and how to reproduce a *"published"* result. In this tutorial, we will demonstrate how to take an exisiting piece of work, stored in a public :term:`workspace`, and develop it further to address a new goal.

Extending an existing CellML model
==================================

In this part of the tutorial, we will once again be making use of the `Noble (1962) <http://www.ncbi.nlm.nih.gov/pmc/articles/PMC1359535/>`_ cardiac cellular electrophysiology model. We will be taking the model and making changes to alter its behaviour. For this, we will be using the same version of the model published in the teaching instance of the repository: `<http://teaching.physiomeproject.org/e/173>`_, but the process described below will also work in the main repository site.

Forking an existing workspace
-----------------------------

.. important::
   It is essential to use a Mercurial client to obtain models from the repository for editing. The Mercurial client is not only able to keep track of all the changes you make (allowing you to back-track if you make any errors), but using a Mercurial client is the only way to add any changes you have made back into the repository.

For this tutorial, we will :term:`fork` an existing workspace. This creates a new workspace owned by you, containing a copy of all the files in the workspace you forked including their complete history. This is equivalent to cloning the workspace, creating a new workspace for yourself, and then pushing the contents of the cloned workspace into your new workspace.

Forking a workspace can be done using the repository web interface. The first step is to find the workspace you wish to fork. As before, we will use the :term:`workspace` from the exposure referenced above, which can be found at: `<http://teaching.physiomeproject.org/w/andre/embc13-n62>`_.

Once you are logged in, click on the :guilabel:`Fork` option in the toolbar, as shown below (1).

.. figure:: images/extending01.png
   :align: center
   :width: 80%

You will be asked to confirm the *fork* action by clicking the :guilabel:`Fork` button (2). You will then be shown the page for your forked workspace.

Cloning your forked workspace
-----------------------------

In order to make changes to your workspace, you have to :term:`clone` it to your own computer. To do this, follow the procedure as described in the :ref:`earlier tutorial <embc13-scenario1-opencor-newWorkspace>`.

Quietening the self excitation
------------------------------

The version of the Noble 1962 model you have just forked and cloned is a model of a Purkinje fibre cell. These cells are capable of acting as pacemaker cells, although usually entrained by the sinoatrial node of the heart. The Noble model reproduces this behavior but is also able to simulate a non-pacing version of the cell model. This is accomplished by decreasing the potassium current which gives rise to the gradual depolarization of the membrane potential seen in the figures from OpenCOR simulations for the model in the previous tutorials. Once the cell is in a quiesent state, we are able to then apply an electrical stimulus to impose our own pacing regime.

If you load the ``n62.cellml`` file from the workspace you have just cloned into OpenCOR, set the duration of the simulation to *5000 ms* (1), and plot the membrane potential ``V``, you will be able to see the effect of altering the value of the variable ``g_K_add`` in the ``parameters`` component. As you increase this value you should see the resting potential decrease and the abolution of the self-exciting mechanism. A value of *0.001 mS_per_mmsq* keeps the resting potential in the physiological range and makes the cell quiesent (2). 

.. figure:: images/extending02.png
   :align: center
   :width: 80%
   
Changes to the parameter value in the simulation view are not currently saved in the model, so to save the change you will need to switch to an editing view (1, 2), find the ``g_K_add`` parameter (3), and set the ``initial_value`` attribute directly (4), as shown below.

.. figure:: images/extending03.png
   :align: center
   :width: 80%
   
Now would be a good time to :ref:`commit your changes <EMBC13-OpenCOR-addingContent>` to your clone of the workspace

Adding an electrical stimulation protocol
-----------------------------------------

Now that we have a quiesent version of the Noble (1962) model, we are able to consider adding our own electrical stimulation protocol. In the :guilabel:`Raw CellML` view, you will see a component with the name ``stimulus_protocol`` as shown below.

.. figure:: images/extending04.png
   :align: center
   :width: 80%
   
As you can see in this snippet of the XML source, there is a stimulus current variable, ``IStim``, which is given a value of *0.0 uA_per_mm2*. In this extension to the model we will replace this simple assignment of no stimulus current with a definition of a periodic applied stimulus. The code example below shows one way to encode such a periodic stimulus current in CellML.

.. code-block:: xml

   <component cmeta:id="stimulus_protocol" name="stimulus_protocol">
     <variable name="IStim" public_interface="out" units="uA_per_mmsq"/>
     <variable name="time" public_interface="in" units="ms"/>
     <variable name="stimPeriod" initial_value="750" units="ms"/>
     <variable name="stimDuration" initial_value="1" units="ms"/>
     <variable name="stimCurrent" initial_value="400" units="uA_per_mmcu"/>
     <variable name="Am" initial_value="200" units="per_mm"/>
     <math xmlns="http://www.w3.org/1998/Math/MathML">
         <apply id="stimulus_calculation"><eq />
             <ci>IStim</ci>
             <piecewise>
                 <piece>
                     <apply><divide/>
                         <ci>stimCurrent</ci>
                         <ci>Am</ci>
                     </apply>
                     <apply><lt/>
                         <apply><rem/>
                             <ci>time</ci>
                             <ci>stimPeriod</ci>
                         </apply>
                         <ci>stimDuration</ci>
                     </apply>
                 </piece>
                 <otherwise>
                     <cn cellml:units="uA_per_mmsq">0.0</cn>
                 </otherwise>
             </piecewise>
         </apply>
     </math>
   </component>

In the above example, we have introduced some new variables to control the frequency, duration, and magnitude of the applied stimulus current. If you replace the ``stimululs_protocol`` component in the ``n62.cellml`` model with the one above, you are able to view a rendering of the mathematics, as below.

.. figure:: images/extending05.png
   :align: center
   :width: 80%

Switching back to the :guilabel:`Simulation` view, you are able to have a play with those variables to ensure they are behaving as expected. **Note:** you may need to set the :guilabel:`Maximum step` for CVODE to *0.1* or change to the Forward Euler integrator in OpenCOR to ensure that your specified stimulus in correctly detected by the numerical integration scheme.

.. figure:: images/extending06.png
   :align: center
   :width: 80%

Now would be a good time to :ref:`commit your changes <EMBC13-OpenCOR-addingContent>` to your clone of the workspace and :ref:`push <embc13-scenario1-opencor-push>` them back to the model repository. You might also want to think about :ref:`sharing your workspace <sharingWorkspaces>` with your neighbors or to have a look at creating an :term:`exposure` for your workspace. To learn how to create exposures, please refer to :ref:`exposing-cellml`.
