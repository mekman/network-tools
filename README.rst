.. -*- mode: rst -*-

.. image:: https://zenodo.org/badge/9689/mekman/network-tools.svg 
:target: http://dx.doi.org/10.5281/zenodo.14803

==============
Network-tools
==============

Network-tools is a collection of python functions for the **analysis of network graphs**. It is especially tailored towards the analysis of functional (**fMRI/MEG/EEG**) and structural (**DTI/DWI**) brain imaging data.

Network-tools provides a full-fledged analysis pipeline, including functions for the data import/export, preprocessing, network construction, statistical comparison and visualization. All functions are fully documented including a huge set of examples.

Main Features
=============

- construction of ``static`` and ``dynamic`` graphs from imaging data
- detection of ``overlapping`` and ``non-overlapping`` network communities 
- extensive set of ``metrics`` to quantify brain networks and communities
- ``statistical comparison`` of graphs including multivariate classification
- ``visualization`` and ``animation`` of network graphs
- Open source, commercially usable **BSD license** (3 clause)

An Example
===========

This code snippet shows how to construct a network graph from a resting-state fMRI time-series and calculate the weighted, local betweenness_centrality::

  >>> from nt import *
  >>> timeseries = load_mri('rest.nii.gz', 'brain_mask.nii.gz')
  >>> adjacency = adj_static(timeseries, measure='corr')
  >>> adjacency_thr = thresholding_prop(adjacency, .1)
  >>> bc = betweenness_centrality(adjacency_thr)

Documentation
==============

To build the documentation you will need ``sphinx``. If not available you can install sphinx like this::

    easy_install -U sphinx

Then change directory to ``nt/doc`` and::

    make html

to make the html documentation.

License
=============
Copyright (C) 2011-2015 Network-tools Developers

- Matthias Ekman <Matthias.Ekman@gmail.com>
- Charl Linssen <charl@turingbirds.com>

Distributed with a BSD license (3 clause); see LICENSE
