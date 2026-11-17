.. meta::
  :description: Learn about the features and capabilities of ROCm for AMD Data Science
  :keywords: Data-analytics, RAPIDS, cuDF, cuGraph, RMM, hipDF, hipGraph, hipRAFT, hipMM, hipVS, Pandas, NetworkX, High-Performance Computing, GPU Acceleration, GPU Computing, Parallel Computing, Scalable Data Science, Python

.. rocmds-index:

********************************************************************
AMD Data Science documentation
********************************************************************

The AMD Data Science toolkit is an open-source collection of GPU-accelerated libraries designed to empower data scientists,
engineers, and researchers to build high-performance data science applications and machine learning workflows on the ROCm platform.
Built upon the core ROCm foundation, AMD Data Science provides a unified, efficient, and scalable environment for end-to-end data science acceleration.

AMD Data Science is a fork of the RAPIDS® open-source project, extended and optimized for AMD GPUs. It enables users to accelerate
both new and existing data science workloads, executing intensive applications with larger datasets at exceptional speed. With the AMD Data Science toolkit,
you can build pre- and post-processing applications for AI models, create big data processing workloads, or accelerate existing data
science pipelines with minimal effort.

AMD Data Science delivers a cohesive set of libraries that target every stage of the data science lifecycle, from data ingestion and transformation
to graph analytics, mathematical computation, vector search, and decision optimization. Each component is optimized for GPU performance while
maintaining user-friendly interfaces compatible with existing data science frameworks and APIs.

The AMD Data Science toolkit includes the following components:

* `hipDF <https://rocm.docs.amd.com/projects/hipDF/en/docs-26.10/>`__ – A GPU-accelerated DataFrame library offering fast and scalable tabular data manipulation, aggregation, and transformation. hipDF enables high-performance preprocessing, feature engineering, and ETL workflows essential for modern data pipelines. It also supports the acceleration of many existing Pandas workflows with little to no code changes.

* `hipMM <https://rocm.docs.amd.com/projects/hipMM/en/docs-26.10/>`__ – The HIP Memory Manager library provides advanced GPU memory management utilities such as efficient allocation, pooling, and data movement to support the various libraries that form part of the AMD Data Science toolkit. 

* `hipRAFT <https://rocm.docs.amd.com/projects/hipRAFT/en/docs-26.10/>`__ – Provides a foundational layer of reusable GPU-accelerated primitives for data science and machine learning, including clustering, dimensionality reduction, and statistical operations. hipRAFT serves as the computational backbone for higher-level data science and AI applications.

* `hipVS <https://rocm.docs.amd.com/projects/hipvs/en/docs-26.10/>`__ – A GPU-accelerated vector search library containing a variety of high-performance approximate and exact nearest-neighbor and clustering algorithms. hipVS integrates seamlessly with DataFrames offered through hipDF, to enable support for a wide variety of data science workloads. 

* `rocOpt <https://rocm.docs.amd.com/projects/rocopt/en/latest/>`__ – rocOpt is an open-source, GPU-accelerated engine for decision optimization on AMD Instinct GPUs through the ROCm software stack. It solves large-scale linear programming (LP), mixed-integer linear programming (MILP), quadratic programming (QP), and vehicle routing problems. 

  .. note::
    
     rocOpt ships unchanged from 26.07 in this release and retains its dependency on the 26.03 component baseline. It remains a fully supported part of AMD Data Science.

* `dask-hip <https://rocm.docs.amd.com/projects/dask-hip/en/docs-26.10/>`__ – A library for deploying and managing Dask workers on HIP-enabled AMD GPU systems. dask-hip adds distributed execution capabilities for scaling GPU-accelerated data science workloads across one or more AMD GPUs.

* `hip-ucxx <https://rocm.docs.amd.com/projects/hip-ucxx/en/docs-26.10/>`__ – A communication component for distributed GPU workflows on AMD platforms. hip-ucxx complements dask-hip by providing UCXX-based communication support for ROCm environments, helping enable distributed and multi-GPU data science workflows across AMD systems.  

The AMD Data Science organization is open and hosted at `https://github.com/AMD-Ecosystem/datascience <https://github.com/AMD-Ecosystem/datascience>`__.

AMD Data Science documentation is organized into the following categories:

.. grid:: 2
  :gutter: 3

  .. grid-item-card:: Installation

    * :ref:`linux-install`

  .. grid-item-card:: Related Content

    * `AMD Data Science blogs <https://rocm.blogs.amd.com/data-science.html>`__
    * :ref:`contributing-to-datascience`
