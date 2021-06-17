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
| SZ3 [2]         | Generic: Can be used on any dataset. Highly customizable.                            | MMD-SZ [10]     | Specialized: Optimized for material molecular dynamics.                                                    |
| SZx [3]        | Generic: Ultra-fast. Not customizable.                                               | SZ-auto [11] | Generic: Version that automatic tunes parameters for optimal compression.                                 |
| cuSZ [7]      | Generic: Version for Nvidia Graphic Processor Unit (GPU) can be used on any dataset. | waveSZ [12]    | Generic: Generic: Version for Field Programmable Gate Array (FPGA). Can be used on any dataset.           |
| kSZ [4]        | Generic: GPU version portable across vendors. Can be used on any dataset.            | vecSZ [6]    | Generic: Version for Single Instruction Multiple Data instruction set in CPU. Can be used on any dataset. |
| Interp-SZ [8] | Specialized: Optimized for seismic imaging (oil and gas).                            | cpSZ [13]     | Specialized: Optimized for fluid flows.                                                                   |
| Pastri-SZ [9] | Specialized: Optimized for quantum chemistry.                                        | DeepSZ [14]  | Specialized: Optimized for Deep Learning.                                                                 |

- [1] SZ1.4/2.1: [https://github.com/szcompressor/SZ](https://github.com/szcompressor/SZ).
- [2] SZ3: [https://github.com/szcompressor/SZ3](https://github.com/szcompressor/SZ3).
- [3] SZx: [https://github.com/szcompressor/SZx](https://github.com/disheng222/SZx).
- [4] kokkosSZ: [https://github.com/szcompressor/kokkosSZ](https://github.com/szcompressor/kokkosSZ).
- [5] Roibin-SZ: [https://github.com/szcompressor/SZ/tree/master/example/roibin_example](https://github.com/szcompressor/SZ/tree/master/example/roibin_example).
- [6] MMD-SZ: [https://github.com/szcompressor/MMD-SZ](https://github.com/szcompressor/MMD-SZ)
- [7] vecSZ: [https://github.com/szcompressor/vecSZ](https://github.com/szcompressor/vecSZ).
- [8] Jiannan Tian, Sheng Di, Kai Zhao, Cody Rivera, Megan Hickman, Robert Underwood, Sian Jin, Xin Liang, Jon Calhoun, Dingwen Tao, and Franck Cappello. “cuSZ: An Efficient GPU Based Error-Bounded Lossy Compression Framework for Scientific Data.” In Proceedings of the 29th International Conference on Parallel Architectures and Compilation Techniques (PACT), 2020. https://github.com/szcompressor/cuSZ
- [9] Kai Zhao, Sheng Di, Maxim Dmitriev, Thierry-Laurent D. Tonellot, Zizhong Chen, and Franck Cappello. “Optimizing Error-Bounded Lossy Compression for Scientiﬁc Data by Dynamic Spline Interpolation.” In 2021 IEEE International Conference on Data Engineering (ICDE), Chania, Crete, Greece, pp. 1643-1654, Apr 19 - 22, 2021.
- [10] Ali Murat Gok, Sheng Di, Yuri Alexeev, Dingwen Tao, Vladimir Mironov, Xin Liang, and Franck Cappello. “Pastri: Error-bounded lossy compression for two-electron integrals in quantum chemistry.” In 2018 IEEE international conference on cluster computing (CLUSTER), pp. 1-11. IEEE, 2018. Best Paper Award.
- [11] Kai Zhao, Sheng Di, Xin Liang, Sihuan Li, Dingwen Tao, Zizhong Chen, and Franck Cappello. “Significantly improving lossy compression for hpc datasets with second-order prediction and parameter optimization.” In Proceedings of the 29th International Symposium on High-Performance Parallel and Distributed Computing (HPDC), pp. 89-100. 2020. https://github.com/szcompressor/SZauto
- [12] Jiannan Tian, Sheng Di, Chengming Zhang, Xin Liang, Sian Jin, Dazhao Cheng, Dingwen Tao, and Franck Cappello. “waveSZ: a hardware-algorithm co-design of efficient lossy compression for scientific data.” In Proceedings of the 25th ACM SIGPLAN Symposium on Principles and Practice of Parallel Programming, pp. 74-88. 2020. https://github.com/szcompressor/SZ_HLS
- [13] Xin Liang, Hanqi Guo, Sheng Di, Franck Cappello, Mukund Raj, Chunhui Liu, Kenji Ono, Zizhong Chen, and Tom Peterka. “Toward Feature-Preserving 2D and 3D Vector Field Compression.” In PacificVis, pp. 81-90. 2020. https://github.com/szcompressor/cpSZ
- [14] Sian Jin, Sheng Di, Xin Liang, Jiannan Tian, Dingwen Tao, and Franck Cappello. “Deepsz: A novel framework to compress deep neural networks by using error-bounded lossy compression.” In Proceedings of the 28th International Symposium on High-Performance Parallel and Distributed Computing (HPDC), pp. 159-170. 2019. https://github.com/szcompressor/deepsz
