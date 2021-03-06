Philosophy
==========

Motivation
----------
The Mississippi Alluvial Plain (MAP) is one of the most import agricultural
regions in the US, and `among the most depleted <https://ngwa.onlinelibrary.wiley.com/doi/abs/10.1111/gwat.12306>`_
in terms of its groundwater resource .
Groundwater modeling with MODFLOW is being used to support future management decisions (e.g. Haugh et al. 2020).
Given the size and heterogeneity of the MAP region, management decisions are best supported by local-scale
models-- inset within a larger regional hydrogeologic framework-- that can be tuned to answer specific
questions. Construction and management of multiple models presents a challenge to project resources, however,
especially if incremental updates to the models are desired as new data become available.

USGS-MAP-gwmodels provides a single code base for preprocessing
input data to the
`USGS Mississippi Alluvial Plain (MAP) project <https://www2.usgs.gov/water/lowermississippigulf/map/>`_ groundwater models.
Input data are derived from other components within the MAP project and from
external sources such as the National Water Information System (NWIS). Preprocessed
data are output in clean formats that are independent of a particular model
grid, allowing the model discretization to be easily changed without rerunning the preprocessing. By having
a single code base that is well tested and documented, we avoid the many of the potential errors and
confusion that are inherent in ad-hoc scripting. A single code base also facilitates reproducability
in the modeling workflow, and incremental updating of the models as new data
become available.


What usgs-map-gwmodels does
-------------------------------------------
Input data from other components within the MAP project and from
external sources such as the National Water Information System (NWIS) are preprocessed
into clean formats that are readable by the `modflow-setup <https://github.com/aleaf/modflow-setup>`_
package, which assembles the actual input files to MODFLOW, and
`modflow-obs <https://github.com/aleaf/modflow-obs>`_, which creates observation input for the
`PEST family of programs <https://pesthomepage.org/pest-suite>`_.

The original data, coming from different sources, is heterogenous and may cover large areas.
The intial preprocessing step performed by USGS-MAP-gwmodels allows the often unwieldy source data to be
kept separate from the model setup workflow. This way, the well-organized and minimal
input data created by USGS-MAP-gwmodels can be included, along with the model input files and build script,
in a self-contained git repository that has everything needed to regenerate a model at
different spatial or temporal discretizations, or with other input modifications. An overview
of the modeling workflow is shown below:

.. raw:: html

    <iframe src="_static/modeling_flow_chart.html/modeling_flow_chart.html" height="550px" width="100%" frameBorder="0" scrolling="no" style="-webkit-transform:scale(1.0);-moz-transform-scale(1.0);"></iframe>



What usgs-map-gwmodels doesn't do
--------------------------------------------------------
USGS-MAP-gwmodels has been developed thus far to support groundwater modeling efforts for
the `Mississippi Alluvial Plain (MAP) project <https://www2.usgs.gov/water/lowermississippigulf/map/>`_.
While many of the features may be transferable
to other water availability modeling, USGS-MAP-gwmodels is not currently intended
to be fully general or comprehensive in terms of the types of input data it supports. If
you are interested in adapting USGS-MAP-gwmodels to your work and would like to see support
added for another type of data, get ahold of us via
`the Issues tab on our GitHub page <https://github.com/aleaf/usgs-map-gwmodels/issues>`_.
Finally, USGS-MAP-gwmodels does not write actual input MODFLOW or PEST. These tasks
are delegated to `modflow-setup <https://github.com/aleaf/modflow-setup>`_ and
`modflow-obs <https://github.com/aleaf/modflow-obs>`_.