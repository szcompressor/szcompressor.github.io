---
title: SZ Lossy Compression
---

## Overview

SZ is a modular parametrizable lossy compressor framework for scientific data (floating point and integers). It has applications in simulations, AI and instruments. It is a production quality software and a research platform for lossy compression. SZ is open and transparent. Open because all interested researchers and students can study or contribute to it. Transparent because all performance improvements are detailed in publications.

SZ can be used for classic use-cases: visualization, accelerating I/O, reducing memory and storage footprint and more advanced use-cases like compression of DNN models and training sets, acceleration of computation, checkpoint/restart, reducing streaming intensity and running efficiently large problems that cannot fit in memory. Other use-cases will augment this list as users find new opportunities to benefit from lossy compression of scientific data.

SZ has implementations on CPU, GPU, and FPGA and is integrated in the main I/O libraries: HFD5, ADIOS, PnetCDF.

The current structure of the SZ framework is represented by the following hierarchy. This figure should help users to select the configuration of SZ corresponding to their needs.

![SZ_Family_Tree](https://user-images.githubusercontent.com/5705572/121612979-6653fd80-ca10-11eb-8c2d-e79a307c5f06.jpg)


#### SZ products and their utilization

| **Product**           | **Utilization**                                                                          | **Product**         | **Utilization**                                                                                               |
|-------------------|--------------------------------------------------------------------------------------|-----------------|-----------------------------------------------------------------------------------------------------------|
| SZ1.4/2.1 [1]  | Generic: Can be used on any dataset. Not customizable.                               | Roibin-SZ [5] | Specialized: Optimized for X-ray crystallography (instrument).                                             |
| SZ3 [2]         | Generic: Can be used on any dataset. Highly customizable.                            | MMD-SZ     | Specialized: Optimized for material molecular dynamics.                                                    |
| SZx [3]        | Generic: Ultra-fast. Not customizable.                                               | SZ-auto [HPDC'20] | Generic: Version that automatic tunes parameters for optimal compression.                                 |
| cuSZ [PACT'20]      | Generic: Version for Nvidia Graphic Processor Unit (GPU) can be used on any dataset. | waveSZ [PPoPP'20]    | Generic: Generic: Version for Field Programmable Gate Array (FPGA). Can be used on any dataset.           |
| kSZ [4]        | Generic: GPU version portable across vendors. Can be used on any dataset.            | vecSZ [6]    | Generic: Version for Single Instruction Multiple Data instruction set in CPU. Can be used on any dataset. |
| Interp-SZ [ICDE'21] | Specialized: Optimized for seismic imaging (oil and gas).                            | cpSZ [PacificVis'20]     | Specialized: Optimized for fluid flows.                                                                   |
| Pastri-SZ [CLUSTER'18] | Specialized: Optimized for quantum chemistry.                                        | DeepSZ [HPDC'19]  | Specialized: Optimized for Deep Learning.                                                                 |

1. SZ: [https://github.com/szcompressor/SZ](https://github.com/szcompressor/SZ).
2. SZ3: [https://github.com/szcompressor/SZ3](https://github.com/szcompressor/SZ3).
3. SZx: [https://github.com/disheng222/SZx](https://github.com/disheng222/SZx).
4. kokkosSZ: [https://github.com/szcompressor/kokkosSZ](https://github.com/szcompressor/kokkosSZ).
5. Roibin-SZ: [https://github.com/szcompressor/SZ/tree/master/example/roibin_example](https://github.com/szcompressor/SZ/tree/master/example/roibin_example).
6. vecSZ: [https://github.com/szcompressor/vecSZ](https://github.com/szcompressor/vecSZ).
