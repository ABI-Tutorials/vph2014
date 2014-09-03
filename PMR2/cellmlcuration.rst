.. _cellmlcuration:

=======================================================
CellML Curation in the legacy Physiome Model Repository
=======================================================

As the Auckland Physiome Repository contains much of the data ported
over from the legacy software products that powered what was called the
CellML Model Repository, the curation system from that system was ported
to Auckland Physiome Repository verbatim. This document describing the
curation aspect of the repository is derived from documentation on the
CellML site.

CellML Model Curation: the Theory
=================================

The basic measure of curation in a CellML model is described by the
curation level of the model document. We have defined four levels of
curation:

- Level 0: not curated.
- Level 1: the CellML model is consistent with the mathematics in the
  original published paper.
- Level 2: the CellML models has been checked for (i) typographical
  errors, (ii) consistency of units, (iii) that all parameters and
  initial conditions are defined, (iv) that the model is not
  over-constrained, in the sense that it contains equations or initial
  values which are either redundant or inconsistent, and (v) that
  running the model in an appropriate simulation environment reproduces
  the results published in the original paper.
- Level 3: the model is checked for the extent to which it satisfies
  physical constraints such as conservation of mass, momentum, charge,
  etc. This level of curation needs to be conducted by specialised
  domain experts.

CellML Model Curation: the Practice
===================================

Our ultimate aim is to complete the curation of all the models in the
repository, ideally to the level that they replicate the results in the
published paper (level 2 curation status).  However, we acknowledge that
for some models this will not be possible.  Missing parameters and
equations are just one limitation; at this point it should also be
emphasised that the process of curation is not just about "fixing the
CellML model" so that it runs in currently available tools.
Occasionally it is possible for a model to be expressed in valid CellML,
but not yet able to be solved by CellML tools. An example is the seminal
Saucerman et al. 2003 model, which contains ODEs as well as a set of
non-linear algebraic equations which need to be solved simultaneously.
The developers of the CellML editing and simulation environment OpenCell
are currently working on addressing these requirements.

The following steps describe the process of curating a CellML model:

- **Step 1:** the model is run through OpenCell and COR.  COR in
  particular is a useful validation tool.  It renders the MathML in a
  human readable format making it much easier to identify any
  typographical errors in the model equations.  COR also provides a
  comprehensive error messaging system which identifies typographical
  errors, missing equations and parameters, and any redundancy in the
  model such as duplicated variables or connections.  Once these errors
  are fixed, and assuming the model is now complete, we compare the
  CellML model equations with those in the published paper, and if they
  match, the CellML model is awarded a single star - or level 1 curation
  status.

- **Step 2:** Assuming the model is able to run in OpenCell and COR, we
  then go onto compare the CellML model simulation output from COR and
  OpenCell with the published results.  This is often a case of
  comparing the graphical outputs of the model with the figures in the
  published paper, and is currently a qualitative process.  If the
  simulation results from the CellML model and the original model match,
  the CellML model is awarded a second star - or level 2 curation
  status.

- **Step 3:** if, at the end of this process, the CellML model is still
  missing parameters or equations, or we are unable to match the
  simulation results with the published paper, we seek help from the
  original model author.  Where possible, we try to obtain the original
  model code, and this often plays an invaluable role in fixing the
  CellML model.

- **Step 4:** Sometimes we have been able to engage the original model
  author further, such that they take over the responsibility of
  curating the CellML model themselves.  Such models include those
  published by Mike Cooling and Franc Sachse.  In these instances the
  CellML model is awarded a third star - or level 3 curation status.
  While this is laudable, ideally we would like to take the curation
  process one step further, such that level 3 curation should be
  performed by a domain expert who is not the author of the original
  publication (i.e., peer review).  This expert would then check the
  CellML model meets the appropriate constraints and expectations for a
  particular type of model.

A point to note is that levels 1 and 2 of the CellML model curation
status may be mutually exclusive - in our experience, it is rare for a
paper describing a model to contain no typographical errors or
omissions.  In this situation, Version 1 of a CellML model usually
satisfies curation level 1 in that it reflects the model as it is
described in the publication - errors included, while subsequent
versions of the CellML model break the requirements for meeting level 1
curation in order to meet the standards of level 2.  Taking this idea
further, this means that a model with 2 yellow stars doesn't necessarily
meet the requirements of level 1 curation but it does meet the
requirements of level 2.  Hopefully this conflict will be resolved when
we replace the current star system with a more meaningful set of
curation annotations.

Ultimately, we would like to encourage the scientific modeling community
- including model authors, journals and publishing houses - to publish
their models in CellML code in the Auckland Physiome Repository
concurrent with the publication of the printed article. This will
eliminate the need for code-to-text-to-code translations and thus avoid
many of the errors which are introduced during the translation process.

CellML Model Simulation: the Theory and Practice
================================================

As part of the process of model curation, it is important to know what
tools were used to simulate (run) the model and how well the model runs
in a specific simulation environment. In this case, the theory and the
practice are essentially the same thing, and carry out a series of
simulation steps which then translate into a confidence level as part of
a simulator's metadata for each model. The four confidence levels are
defined as:

- Level 0: not curated (no stars);
- Level 1: the model loads and runs in the specified simulation
  environment (1 star);
- Level 2: the model produces results that are qualitatively similar to
  those previously published for the model (2 stars);
- Level 3: the model has been quantitatively and rigorously verified as
  producing identical results to the original published model (3 stars).
