# AMD Data Science 26.10 release notes

AMD Data Science 26.10 updates the toolkit to ROCm 10.0.0 and brings the
core libraries to their RAPIDS 26.06 upstream baselines. The release adds broader
AMD GPU coverage, modernized memory-resource interfaces, improved distributed
GPU communication, and expanded vector-search and machine-learning
functionality.

- [AMD Data Science release highlights](#amd-data-science-release-highlights)
- [System requirements](#system-requirements)
- [AMD Data Science components](#amd-data-science-components)
- [Detailed component changelogs](#detailed-component-changelogs)
- [Important compatibility notes](#important-compatibility-notes)

## AMD Data Science release highlights

The 26.10 release includes the following major updates and highlights:

* Support for upstream RAPIDS 26.06 components. 
* ROCm 10.0.0 support across updated components. 
* Support for Python 3.11, 3.12, and 3.13.
* Improved hipBLASLt fallback behavior and numerical stability for randomized SVD on `gfx942` in hipRAFT.

## System requirements

For the 26.10 release, the AMD Data Science components support the ROCm 10.0.0 release. Refer to the {doc}`Compatibility matrix <compatibility-matrix>` to verify supported AMD Instinct GPUs, operating systems, and ROCm versions.

## AMD Data Science components

The following table lists AMD Data Science component versions for the 26.10 release, including any version
changes. Click {fab}`github` to go to the component's source code on GitHub.

<div class="pst-scrollable-table-container">
    <table id="rocm-rn-components" class="table">
        <thead>
            <tr>
           <th>Name</th>
           <th>Version</th>
           <th>GitHub</th>
            </tr>
        </thead>
        <colgroup>
            <col span="1">
            <col span="1">
        </colgroup>
        <tbody class="amd-ds-components">
            <tr>
                <td><a href="https://rocm.docs.amd.com/projects/hipDF/en/docs-26.10/">hipDF</a></td>
                <td>3.0.0&nbsp;&Rightarrow;&nbsp;<a href="#hipdf-4-0-0">4.0.0</a></td>
                <td><a href="https://github.com/AMD-Ecosystem/hipDF"><i class="fab fa-github fa-lg"></i></a></td>
            </tr>
            <tr>
                <td><a href="https://rocm.docs.amd.com/projects/hipMM/en/docs-26.10/">hipMM</a></td>
                <td>4.0.0&nbsp;&Rightarrow;&nbsp;<a href="#hipmm-5-0-0">5.0.0</a></td>
                <td><a href="https://github.com/AMD-Ecosystem/hipMM"><i class="fab fa-github fa-lg"></i></a></td>
            </tr>
            <tr>
                <td><a href="https://rocm.docs.amd.com/projects/hipRaft/en/docs-26.10/">hipRAFT</a></td>
                <td>1.0.0&nbsp;&Rightarrow;&nbsp;<a href="#hipraft-2-0-0">2.0.0</a></td>
                <td><a href="https://github.com/AMD-Ecosystem/hipRaft"><i class="fab fa-github fa-lg"></i></a></td>
            </tr>
            <tr>
                <td><a href="https://rocm.docs.amd.com/projects/hipVS/en/docs-26.10/">hipVS</a></td>
                <td>1.0.0&nbsp;&Rightarrow;&nbsp;<a href="#hipvs-2-0-0">2.0.0</a></td>
                <td><a href="https://github.com/AMD-Ecosystem/hipVS"><i class="fab fa-github fa-lg"></i></a></td>
            </tr>
            <tr>
                <td><a href="https://rocm.docs.amd.com/projects/dask-hip/en/docs-26.10/">dask-hip</a></td>
                <td>1.0.0&nbsp;&Rightarrow;&nbsp;<a href="#dask-hip-2-0-0">2.0.0</a></td>
                <td><a href="https://github.com/AMD-Ecosystem/dask-hip"><i class="fab fa-github fa-lg"></i></a></td>
            </tr>
            <tr>
                <td><a href="https://rocm.docs.amd.com/projects/hip-ucxx/en/docs-26.10/">hip-ucxx</a></td>
                <td>0.1.0&nbsp;&Rightarrow;&nbsp;<a href="#hip-ucxx-2-0-0">0.2.0</a></td>
                <td><a href="https://github.com/AMD-Ecosystem/hip-ucxx"><i class="fab fa-github fa-lg"></i></a></td>
            </tr>
        </tbody>
    </table>
</div>

## Detailed component changelogs

The following sections describe key changes to AMD Data Science components.

### hipDF 4.0.0

hipDF now follows the RAPIDS cuDF 26.06 API baseline, improving portability
for applications that use cuDF-compatible DataFrame and Python interfaces.
This release adds ROCm 10.0.0 and `gfx950` support and expands AMD PyPI
packaging across the core C++ and Python libraries and the Dask integration.

hipDF continues to provide GPU-native Series and DataFrame operations,
including joins, aggregations, window operations, string and list processing,
and CSV, JSON, Parquet, ORC, HDF5, Feather, and Avro I/O.

### hipMM 5.0.0

hipMM adopts the upstream RMM 26.06 memory-resource model and the unified CCCL
memory-resource design. This provides a more consistent foundation for
allocation, pooling, tracking, and interoperability across AMD Data Science
components.

This release also modernizes device-buffer and allocator interfaces, updates
the Python bindings, and provides AMD PyPI packages for both the C++ library
and Python API. Applications using older `device_memory_resource` APIs might
need migration updates.

### hipVS 2.0.0

hipVS upgrades from cuVS 25.10 to cuVS 26.06 and makes multi-GPU, multi-node,
and wave32 execution official rather than experimental. The release brings
several capabilities that make vector-search workloads more portable and
more useful on AMD GPUs:

- End-to-end FP64 brute-force k-nearest-neighbor support across the C++, C,
  and Python APIs.
- ROCm-native JIT-LTO support through hipRTC and hipModule for CAGRA,
  IVF-Flat, IVF-PQ, IVF-SQ, and user-defined metrics.
- A Composable Kernel backend for fused FP32 L2, cosine, and inner-product
  distance calculations, including skinny-K optimization.
- Improved FP32 NN-Descent recall through a native HIP local-join kernel.
- IVF-SQ, PCA, KDE, and user-defined-distance APIs, plus expanded CAGRA,
  KMeans, NN-Descent, HNSW, and all-neighbors functionality.
- Rust `hipvs` bindings updated for the 26.06 API, including Vamana and
  DiskANN support.
- Manylinux wheels for Python 3.11 and later and a new
  `HIPVS_ENABLE_CK_BACKEND` build option.

The release also hardens index deserialization against malicious inputs and
improves correctness for wave32, RDNA3 CK distance paths, sparse metrics,
multi-GPU JIT/UDF execution, and graph-search workloads.

Known limitations: INT8 IVF-PQ coarse search is unsupported and FP64
brute-force search uses the tiled, non-fused kNN path.

### hipRAFT 2.0.0

hipRAFT upgrades to the RAFT 26.06 baseline and adds PCA, truncated SVD, and
sparse randomized SVD primitives. It also exposes NumPy serialization helpers
and adopts CCCL-based memory-resource handling, including support for tracking
resources.

This release improves hipBLASLt fallback behavior, numerical stability for
randomized SVD on `gfx942`, `gfx90a` builds, histogram initialization, and
stream synchronization. Python packages are built with `scikit-build-core`
and are published for Python 3.11, 3.12, and 3.13.

### dask-hip 2.0.0

dask-hip improves deployment of Dask workloads across AMD GPU systems. It
provides one-worker-per-GPU placement with `HIP_VISIBLE_DEVICES`, CPU
affinity, UCX communication, GPU-memory spilling, hipMM pool integration, and
command-line worker management.

This release updates the dask-cuda 26.06 baseline, removes deprecated upstream
components, and replaces CUDA-specific compatibility dependencies with
HIP-aware Python interoperability. This allows existing Dask GPU workflows
to be adapted to AMD systems with fewer application changes.

### hip-ucxx 0.2.0

hip-ucxx updates its UCXX baseline to 0.50.01 and provides the communication
layer for distributed AMD GPU workloads. It supports tag matching, streams,
active messages, remote memory access, and GPU-direct transfers over
ROCm-enabled UCX transports.

This release includes asynchronous Python bindings, the
`distributed-ucxx` Dask backend, and support for hipMM device buffers. It
also updates the AMD PyPI packages and build requirements for ROCm 10.0.0.

## Important compatibility notes

- Use isolated AMD Data Science environments when installing the AMD PyPI
  packages.
- hipVS INT8 IVF-PQ coarse search is not supported.
- hipDF has known limitations around some `cudf.pandas` configurations under
  heavy XNACK memory pressure.
- Some advanced hipRAFT distributed and randomized-SVD APIs remain
  unsupported or experimental.
