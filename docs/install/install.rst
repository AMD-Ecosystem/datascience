.. meta::
    :description: AMD Data Science installation
    :keywords: Data-analytics, RAPIDS, cuDF, cuGraph, RMM, hipDF, hipGraph, hipMM, Pandas, NetworkX, High-Performance Computing, GPU Acceleration, GPU Computing, Parallel Computing, Scalable Data Science, Python

.. _linux-install:

**************************************************************************************
Installing AMD Data Science
**************************************************************************************

This topic provides brief guidance and recommendations on setting up your environment and installing AMD Data Science components.

System requirements
===================

The following are the AMD Data Science release compatibilities and system requirements: 

* `ROCm 10.0.0 <https://rocm.docs.amd.com/en/docs-10.0.0/install/rocm.html>`__
* Operating Systems: Ubuntu 24.04, Ubuntu 22.04
* AMD Instinct GPUs:

  - MI355X (GPU target gfx950)
  - MI325X / MI300X (GPU target gfx942)
  - MI250 / MI210 (GPU target gfx90a)
  
* Python versions: 3.11, 3.12, 3.13

Installation instructions
=========================

Each AMD Data Science component must be separately installed as needed. You can find the installation instructions for each component as follows: 

* `hipDF Installation instructions <https://rocm.docs.amd.com/projects/hipDF/en/docs-26.10/install/INSTALL.html>`__
* `hipMM Installation instructions <https://rocm.docs.amd.com/projects/hipMM/en/docs-26.10/install/INSTALL.html>`__
* `hipRAFT Installation instructions <https://rocm.docs.amd.com/projects/hipRaft/en/docs-26.10/install/install.html>`__
* `hipVS Installation instructions <https://rocm.docs.amd.com/projects/hipVS/en/docs-26.10/install/install.html>`__
* `rocOpt Installation instructions <https://rocm.docs.amd.com/projects/rocopt/en/docs-26.07/install/install_rocopt.html>`__

.. note::
    
    rocOpt only supports the ROCm 7.2.3 release, and works with other components from the Data Science 26.03 release.
    
* `dask-hip Installation instructions <https://rocm.docs.amd.com/projects/dask-hip/en/docs-26.10/install/install.html>`__
* `hip-ucxx Installation instructions <https://rocm.docs.amd.com/projects/hip-ucxx/en/docs-26.10/install/install.html>`__
