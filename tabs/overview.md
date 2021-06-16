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
| SZ1.4/2.1 [1]  | Generic: Can be used on any dataset. Not customizable.                               | Roibin-SZ [5] | Specialized: Optimized for X-ray crystallography (instrument)                                             |
| SZ3 [2]         | Generic: Can be used on any dataset. Highly customizable.                            | MMD-SZ [13]    | Specialized: Optimized for material molecular dynamics                                                    |
| SZx [3]         | Generic: Ultra-fast. Not customizable.                                               | SZ-auto [10] | Generic: Version that automatic tunes parameters for optimal compression.                                 |
| cuSZ [11]      | Generic: Version for Nvidia Graphic Processor Unit (GPU) can be used on any dataset. | waveSZ [9]    | Generic: Generic: Version for Field Programmable Gate Array (FPGA). Can be used on any dataset.           |
| kSZ [4]         | Generic: GPU version portable across vendors. Can be used on any dataset.            | vecSZ     | Generic: Version for Single Instruction Multiple Data instruction set in CPU. Can be used on any dataset. |
| Interp-SZ [12] | Specialized: Optimized for seismic imaging (oil and gas).                            | cpSZ [6]     | Specialized: Optimized for fluid flows.                                                                   |
| Pastri-SZ [7] | Specialized: Optimized for quantum chemistry.                                        | DeepSZ [8]  | Specialized: Optimized for Deep Learning.                                                                 |

#### References
[1] SZ - an error bounded lossy compressor: https://github.com/szcompressor/SZ.
[2] SZ3: https://github.com/szcompressor/SZ3.
[3] SZx - an ultra-fast error-bounded lossy compressor: https://github.com/disheng222/SZx.
[4] kokkosSZ: a portable accelerator implementation of SZ using kokkos programming model: https://github.com/szcompressor/kokkosSZ.
[5] Robin-SZ: https://szcompressor.org/tabs/software.
[6] cpSZ: a lossy compressor with critical points preserved for vector fields: https://github.com/szcompressor/cpSZ.
[7] Ali Murat Gok, Sheng Di, Yuri Alexeev, Dingwen Tao, Vladimir Mironov, and Franck Cappello, PaSTRI: Error-bounded Lossy Compression for Two-Electron Integrals in Quantum Chemistry, in IEEE CLUSTER 2018, 2018, Pages 1-11. (Best paper award).
[8] Sian Jin, Sheng Di, Xin Liang, Jiannan Tian, Dingwen Tao, Franck Cappello, DeepSZ: A Novel Framework to Compress Deep Neural Networks by Using Error-Bounded Lossy Compression, Proceedings of the 28th ACM International Symposium on High-Performance Parallel and Distributed Computing (ACM HPDC19), Phoenix, AZ, USA, June 24 - 28, 2019. https://github.com/szcompressor/DeepSZ.
[9] Jiannan Tian, Sheng Di, Chengming Zhang, Xin Liang, Sian Jin, Dazhao Cheng, Dingwen Tao, and Franck Cappello, waveSZ: A Hardware-Algorithm Co-Design of Efficient Lossy Compression for Scientific Data, Proceedings of the 25th ACM SIGPLAN Symposium on Principles and Practice of Parallel Programming (ACM PPoPP2020), San Diego, California, USA, February 22-26, 2020. https://github.com/szcompressor/SZ_HLS.
[10] Kai Zhao, Sheng Di, Maxim Dmitriev, Thierry-Laurent D. Tonellot, Zizhong Chen, and Franck Cappello, Optimizing Error-Bounded Lossy Compression for Scientiﬁc Data by Dynamic Spline Interpolation, Proceeding of the 37th IEEE International Conference on Data Engineering (ICDE2021), Chania, Crete, Greece, Apr 19 - 22, 2021. https://github.com/szcompressor/SZauto.
[11] Jiannan Tian, Sheng Di, Kai Zhao, Cody Rivera, Megan Hickman, Robert Underwood, Sian Jin, Xin Liang, Jon Calhoun, Dingwen Tao, and Franck Cappello, cuSZ: An Efficient GPU Based Error-Bounded Lossy Compression Framework for Scientific Data, Proceedings of the 29th International Conference on Parallel Architectures and Compilation Techniques (PACT'20), 2020, Pages 3–15. https://github.com/szcompressor/cuSZ.
[12] Kai Zhao, Sheng Di, Maxim Dmitriev, Thierry-Laurent D. Tonellot, Zizhong Chen, and Franck Cappello, Optimizing Error-Bounded Lossy Compression for Scientiﬁc Data by Dynamic Spline Interpolation, Proceeding of the 37th IEEE International Conference on Data Engineering (ICDE2021), Chania, Crete, Greece, Apr 19 - 22, 2021.
[13] MDZ: an efficient error-bounded lossy compressor for molecular dynamics simulations of materials.
