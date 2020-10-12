# SZ Lossy Compression
## Overview
SZ is a modular parametrizable lossy compressor framework for scientific data (floating point and integers). It has applications in simulations, AI and instruments. It is a production quality software and a research platform for lossy compression. SZ is open and transparent. Open because all interested researchers and students can study or contribute to it. Transparent because all performance improvements are detailed in publications.

SZ can be used for classic use-cases: visualization, accelerating I/O, reducing memory and storage footprint and more advanced use-cases like compression of DNN models and training sets, acceleration of computation, checkpoint/restart, reducing streaming intensity and running efficiently large problems that cannot fit in memory. Other use-cases will augment this list as users find new opportunities to benefit from lossy compression of scientific data.

SZ has implementations on CPU, GPU, and FPGA and is integrated in the main I/O libraries: HFD5, ADIOS, PnetCDF.

The current structure of the SZ framework is represented by the following hierarchy. This figure should help users to select the configuration of SZ corresponding to their needs.

![SZ_Family_Tree](https://user-images.githubusercontent.com/5705572/91900477-9ab1b680-ec53-11ea-97bf-5cab7f2c6877.jpg)

## News
- 10/05/2020: [SZ-2.1.10](https://github.com/szcompressor/SZ/releases/download/v2.1.10/sz-2.1.10.tar.gz) has been released.
- 09/27/2020: [cuSZ-0.1.2](https://github.com/szcompressor/cuSZ/releases/download/v0.1.2/cuSZ-0.1.2.tar.gz) has been released. 
- 09/04/2020: [QCAT-1.0](https://github.com/szcompressor/qcat/releases/download/v1.0/qcat-1.0.tar.gz) has been released. 
- 08/24/2020: [DeepSZ-0.1](https://github.com/szcompressor/DeepSZ/releases/download/v0.1/DeepSZ-0.1.tar.gz) has been released.
- 07/15/2020: Our [cuSZ paper](https://arxiv.org/abs/2007.09625) has been accepted by PACT'20.

## Software

- SZ (CPU version): [https://github.com/szcompressor](https://github.com/szcompressor/SZ).
- cuSZ (CUDA version): [https://github.com/szcompressor/cuSZ](https://github.com/szcompressor/cuSZ). 
- kSZ (Kokkos version): [https://github.com/szcompressor/kokkosSZ](https://github.com/szcompressor/kokkosSZ).
- DeepSZ (for DNN model): [https://github.com/szcompressor/DeepSZ](https://github.com/szcompressor/DeepSZ).
- QCAT (Quick Compression Analysis Toolkit): [https://github.com/szcompressor/qcat](https://github.com/szcompressor/qcat).

## Team
### Core-group
#### (Lead) Argonne National Laboratory
[Dr. Franck Cappello](https://www.anl.gov/profile/franck-cappello), [Dr. Sheng Di](https://www.mcs.anl.gov/~shdi/), [Dr. Ali Murat Gok](https://www.anl.gov/profile/ali-murat-gok)

#### Washington State University
[Dr. Dingwen Tao](https://www.dingwentao.com/), Jiannan Tian, Cody Rivera, Sian Jin, Chengming Zhang

#### University of California, Riverside
Kai Zhao, Sihuan Li, Jinyang Liu

#### Clemson Univerity
[Dr. Jon Calhoun](http://jonccal.people.clemson.edu/), Robert Underwood

#### Missouri University of Science and Technology
[Dr. Xin Liang](https://www.cs.ucr.edu/~xlian007/)

### Researchers
[Dr. Martin Herbordt](http://people.bu.edu/herbordt/) (Boston University), Qingqing Xiong (Boston University)

## SZ Compression Ratio, Quality, and Speed

### Rate-Distortion Comparison

SZ has excellent rate-distortion performance, or quality per bit of compressed storage. The below published figures show the compression quality and speed of SZ and other erorr-bounded lossy compressors. The figures show the compressed size in bits per value (higher is better), peak signal to noise ratio (PSNR) in decibels (higher is better), structural similarity (SSIM) index (higher is better), pearson correlation, and compression/decompression speed in uncompressed megabytes per second (higher is better). 

<img width="500" alt="distortion-nyx-dark-matter" src="https://user-images.githubusercontent.com/5705572/95693406-0dae3580-0be1-11eb-9f05-0ce8b61dd9a2.png"> 

<img width="500" alt="distortion-nyx-velocity" src="https://user-images.githubusercontent.com/5705572/95693411-1272e980-0be1-11eb-9a6f-bd8b80bdafd8.png">

<img width="500" alt="distortion-hurricane-cloud" src="https://user-images.githubusercontent.com/5705572/95693413-16067080-0be1-11eb-88f3-8e920aef85e1.png">

<img width="500" alt="rate-distortion-sz-zfp" src="https://user-images.githubusercontent.com/5705572/95693513-a2189800-0be1-11eb-82c9-f7e4ed8dca4f.png">

### Pearson Correlation Comparison

| fields              | SZ2.0       | SZ1.4       | ZFP         | Comp Ratio   |
|---------------------|-------------|-------------|-------------|--------------|
| dark matter density | 0.959274616 | 0.939890773 | 0.763353467 | 58:1         |
| baryon density      | 0.999537914 | 0.986076774 | 0.999529095 | 66:1         |
| temperature         | 0.992798653 | 0.870542883 | 0.995984391 | 66:1         |
| velocity_x          | 0.999961851 | 0.996793357 | 0.999871972 | 70:1         |
| velocity_y          | 0.999944697 | 0.997787266 | 0.999912867 | 70:1         |
| velocity_z          | 0.999867946 | 0.992133964 | 0.999826937 | 63:1         |

### Compression/Decompression Speed Comparison
<img width="550" alt="speed-sz-cusz" src="https://user-images.githubusercontent.com/5705572/95693991-3c79db00-0be4-11eb-9523-d2152b6bc936.png">

### I/O Performance Comparison
<img width="550" alt="I:O-sz-zfp" src="https://user-images.githubusercontent.com/5705572/95694361-9085bf00-0be6-11eb-9f30-9357ac5e6f22.png">

## Publication

### 2016
- [**IPDPS'16**] Sheng Di and Franck Cappello. "Fast error-bounded lossy HPC data compression with SZ." In 2016 IEEE International Parallel and Distributed Processing Symposium (IPDPS), pp. 730-739. IEEE, 2016.

### 2017
- [**IPDPS'17**] Dingwen Tao, Sheng Di, Zizhong Chen, and Franck Cappello. "Significantly improving lossy compression for scientific data sets based on multidimensional prediction and error-controlled quantization." In 2017 IEEE International Parallel and Distributed Processing Symposium (IPDPS), pp. 1129-1139. IEEE, 2017.
- [**BigData'17**] Dingwen Tao, Sheng Di, Zizhong Chen, and Franck Cappello. "In-Depth Exploration of Single-Snapshot Lossy Compression Techniques for N-Body Simulations." In Proceedings of the 2017 IEEE International Conference on Big Data (BigData2017), Boston, MA, USA, December 11 - 14, 2017.
- [**DRBSD-1**] Dingwen Tao, Sheng Di, Zizhong Chen, and Franck Capello. "Exploration of Pattern-Matching Techniques for Lossy Compression on Cosmology Simulation Data Sets." In Proceedings of the 1st International Workshop on Data Reduction for Big Scientific Data (DRBSD=1) in Conjunction with ISC'17, Frankfurt, Germany, June 22, 2017.
- [**TPDS**] Sheng Di and Franck Cappello. "Optimization of Error-Bounded Lossy Compression for Hard-to-Compress HPC Data." IEEE Transactions on Parallel and Distributed System 29, no. 1 (2017): 129-143.

### 2018
- [**HPDC'18**] Dingwen Tao, Sheng Di, Xin Liang, Zizhong Chen, and Franck Cappello. "Improving performance of iterative methods by lossy checkponting." In Proceedings of the 27th International Symposium on High-Performance Parallel and Distributed Computing (HPDC), pp. 52-65. 2018.
- [**BigData'18**] Xin Liang, Sheng Di, Dingwen Tao, Sihuan Li, Shaomeng Li, Hanqi Guo, Zizhong Chen, and Franck Cappello. "Error-controlled lossy compression optimized for high compression ratios of scientific datasets." In 2018 IEEE International Conference on Big Data (Big Data), pp. 438-447. IEEE, 2018.
- [**BigData'18**] Sihuan Li, Sheng Di, Xin Liang, Zizhong Chen, Franck Cappello. "Optimizing Lossy Compression with Adjacent Snapshots for N-body Simulation." In 2018 IEEE International Conference on Big Data (Big Data), pp. 428-437. IEEE, 2018.
- [**CLUSTER'18**] Ali Murat Gok, Sheng Di, Yuri Alexeev, Dingwen Tao, Vladimir Mironov, Xin Liang, and Franck Cappello. "Pastri: Error-bounded lossy compression for two-electron integrals in quantum chemistry." In 2018 IEEE international conference on cluster computing (CLUSTER), pp. 1-11. IEEE, 2018. _Best Paper Award_
- [**CLUSTER'18**] Xin Liang, Sheng Di, Dingwen Tao, Zizhong Chen, and Franck Cappello. "An efficient transformation scheme for lossy data compression with point-wise relative error bound." In 2018 IEEE International Conference on Cluster Computing (CLUSTER), pp. 179-189. IEEE, 2018. _Best Area Paper Award_
- [**CLUSTER'18**] Dingwen Tao, Sheng Di, Xin Liang, Zizhong Chen, and Franck Cappello. "Fixed-psnr lossy compression for scientific data." In 2018 IEEE International Conference on Cluster Computing (CLUSTER), pp. 314-318. IEEE, 2018.
- [**DRBSD-4**] Xin Liang, Sheng Di, Dingwen Tao, Sihuan Li, Zizhong Chen, Franck Cappello. "Improving In-situ Lossy Compression with Spatio-Temporal Decimation based on SZ Model." In Proceedings of the 4th International Workshop on Data Reduction for Big Scientific Data (DRBSD-4), in conjunction with the International Conference for High Performance computing, Networking, Storage and Analysis (SC).
- [**DRBSD-4**] Xin-Chuan Wu, Sheng Di, Franck Cappello, Hal Finkel, Yuri Alexeev, Frederic T. Chong. "Amplitude-Aware Lossy Compression for Quantum Circuit Simulation." In Proceedings of the 4th International Workshop on Data Reduction for Big Scientific Data (DRBSD-4), in conjunction with the International Conference for High Performance computing, Networking, Storage and Analysis (SC).
- [**PMES'18**] Xin-Chuan Wu, Sheng Di, Franck Cappello, Hal Finkel, Yuri Alexeev, Frederic T. Chong. "Memory-Efficient Quantum Circuit Simulation by Using Lossy Data Compression." The 3rd International Workshop on Post-Moore Era Supercomputing (PMES), in conjunction with the International Conference for High Performance computing, Networking, Storage and Analysis (SC).
- [**TPDS**] Sheng Di, Dingwen Tao, Xin Liang, and Franck Cappello. "Efficient lossy compression for scientific data based on pointwise relative error bound." IEEE Transactions on Parallel and Distributed Systems 30, no. 2 (2018): 331-345.

### 2019
- [**HPDC'19**] Sian Jin, Sheng Di, Xin Liang, Jiannan Tian, Dingwen Tao, and Franck Cappello. "Deepsz: A novel framework to compress deep neural networks by using error-bounded lossy compression." In Proceedings of the 28th International Symposium on High-Performance Parallel and Distributed Computing (HPDC), pp. 159-170. 2019.
- [**MSST'19**] Xiangyu Zou, Tao Lu, Wen Xia, Xuan Wang, Weizhe Zhang, Sheng Di, Dingwen Tao, and Franck Cappello. "Accelerating relative-error bounded lossy compression for hpc datasets with precomputation-based mechanisms." In 2019 35th Symposium on Mass Storage Systems and Technologies (MSST), pp. 65-78. IEEE, 2019.
- [**FCCM'19**] Xiong, Qingqing, Rushi Patel, Chen Yang, Tong Geng, Anthony Skjellum, and Martin C. Herbordt. "Ghostsz: A transparent fpga-accelerated lossy compression framework." In 2019 IEEE 27th Annual International Symposium on Field-Programmable Custom Computing Machines (FCCM), pp. 258-266. IEEE, 2019.
- [**CLUSTER'19**] Xin Liang, Sheng Di, Dingwen Tao, Sihuan Li, Bogdan Nicolae, Zizhong Chen, and Franck Cappello. "Improving performance of data dumping with lossy compression for scientific simulation." In 2019 IEEE International Conference on Cluster Computing (CLUSTER), pp. 1-11. IEEE, 2019.
- [**CLUSTER'19**] Pavlo Triantafyllides, Tasmia Reza, and Jon C. Calhoun. "Analyzing the Impact of Lossy Compressor Variability on Checkpointing Scientific Simulations." In 2019 IEEE International Conference on Cluster Computing (CLUSTER), pp. 1-5. IEEE, 2019.
- [**SC'19**] Xin Liang, Sheng Di, Sihuan Li, Dingwen Tao, Bogdan Nicolae, Zizhong Chen, and Franck Cappello. "Significantly improving lossy compression quality based on an optimized hybrid prediction model." In Proceedings of the International Conference for High Performance Computing, Networking, Storage and Analysis (SC), pp. 1-26. 2019.
- [**SC'19**] Xin-Chuan Wu, Sheng Di, Emma Maitreyee Dasgupta, Franck Cappello, Hal Finkel, Yuri Alexeev, and Frederic T. Chong. "Full-state quantum circuit simulation by using data compression." In Proceedings of the International Conference for High Performance Computing, Networking, Storage and Analysis (SC), pp. 1-24. 2019.
- [**HPCC'19**] Zou, Xiangyu, Tao Lu, Sheng Di, Dingwen Tao, Wen Xia, Xuan Wang, Weizhe Zhang, and Qing Liao. "Accelerating Lossy Compression on HPC datasets via Partitioning Computation for Parallel Processing." In 2019 IEEE 21st International Conference on High Performance Computing and Communications(HPCC), pp. 1791-1797. IEEE, 2019.
- [**TPDS**] Dingwen Tao, Sheng Di, Xin Liang, Zizhong Chen, and Franck Cappello. "Optimizing lossy compression rate-distortion from automatic online selection between sz and zfp." IEEE Transactions on Parallel and Distributed Systems 30, no. 8 (2019): 1857-1871.
- [**IJHPCA**] Franck Cappello, Sheng Di, Sihuan Li, Xin Liang, Ali Murat Gok, Dingwen Tao, Chun Hong Yoon, Xin-Chuan Wu, Yuri Alexeev, and Frederic T. Chong. "Use cases of lossy compression for floating-point data in scientific data sets." The International Journal of High Performance Computing Applications 33, no. 6 (2019): 1201-1220.
- [**DRBSD-5**] Tasmia Reza, Kristopher Keipert, Sheng Di, Xin Liang, Jon C. Calhoun, Franck Cappello. "Analyzing the Performance and Accuracy of LossyCheckpointing on Sub-iteration of NWChem." In Proceedings of the 5th International Workshop on Data Reduction for Big Scientific Data (DRBSD-5), in conjunction with the International Conference for High Performance computing, Networking, Storage and Analysis (SC).

### 2020
- [**PPoPP'20**] Jiannan Tian, Sheng Di, Chengming Zhang, Xin Liang, Sian Jin, Dazhao Cheng, Dingwen Tao, and Franck Cappello. "waveSZ: a hardware-algorithm co-design of efficient lossy compression for scientific data." In Proceedings of the 25th ACM SIGPLAN Symposium on Principles and Practice of Parallel Programming, pp. 74-88. 2020.
- [**HPDC'20**] Kai Zhao, Sheng Di, Xin Liang, Sihuan Li, Dingwen Tao, Zizhong Chen, and Franck Cappello. "Significantly improving lossy compression for hpc datasets with second-order prediction and parameter optimization." In Proceedings of the 29th International Symposium on High-Performance Parallel and Distributed Computing (HPDC), pp. 89-100. 2020.
- [**PacificVis'20**] Xin Liang, Hanqi Guo, Sheng Di, Franck Cappello, Mukund Raj, Chunhui Liu, Kenji Ono, Zizhong Chen, and Tom Peterka. "Toward Feature-Preserving 2D and 3D Vector Field Compression." In PacificVis, pp. 81-90. 2020.
- [**IPDPS'20**] Robert Underwood, Sheng Di, Jon Calhoun, and Franck Cappello. "FRaZ: A Generic High-Fidelity Fixed-Ratio Lossy Compression Framework for Scientific Floating-point Data." In 2020 IEEE International Parallel and Distributed Processing Symposium (IPDPS), pp. 567-577. IEEE, 2020.
- [**IPDPS'20**] Sian Jin, Pascal Grosset, Christopher M Biwer, Jesus Pulido, Jiannan Tian, Dingwen Tao, and James Ahrens. "Understanding GPU-Based Lossy Compression for Extreme-Scale Cosmological Simulations." In 2020 IEEE International Parallel and Distributed Processing Symposium (IPDPS), pp. 105-115. IEEE, 2020.
- [**PACT'20**] Jiannan Tian, Sheng Di, Kai Zhao, Cody Rivera, Megan Hickman, Robert Underwood, Sian Jin, Xin Liang, Jon Calhoun, Dingwen Tao, and Franck Cappello. "cuSZ: An Efficient GPU Based Error-Bounded Lossy Compression Framework for Scientific Data." In Proceedings of the 29th International Conference on Parallel Architectures and Compilation Techniques (PACT), 2020.
- [**SMC'20**] Franck Cappello, Sheng Di, Ali M. Gok, "Fulfilling the Promises of Lossy Compression forScientific Applications", Smoky Mountain Computational Science and Engineering Conference (SMC), 2020.
- [**ICPP'20**] Zhenbo Hu, Xiangyu Zou, Wen Xia, Sian Jin, Dingwen Tao, Yang Liu, Weizhe Zhang, and Zheng Zhang. "Delta-DNN: Efficiently Compressing Deep Neural Networks via Exploiting Floats Similarity." In 49th International Conference on Parallel Processing (ICPP), Article 40, 1–12. ACM, 2020.
- [**CLUSTER'20**] Sihuan Li, Sheng Di, Kai Zhao, Xin Liang, Zizhong Chen, and Franck Cappello. "Towards End-to-end SDC Detection for HPC Applications Equipped with Lossy Compression." In 2020 IEEE International Conference on Cluster Computing (CLUSTER). IEEE, 2019.
- [**TPDS**] Xiangyu Zou, Tao Lu, Wen Xia, Xuan Wang, Weizhe Zhang, Haijun Zhang, Sheng Di, Dingwen Tao, and Franck Cappello. "Performance Optimization for Relative-Error-Bounded Lossy Compression on Scientific Data." IEEE Transactions on Parallel and Distributed Systems 31, no. 7 (2020): 1665-1680.


<!--## Who are using SZ

| Software                                             | Institution            | Referece                                                                |
|------------------------------------------------------|------------------------|-------------------------------------------------------------------------|
| Software Stack in Division of Information Technology | university of maryland | http://devhpcc.umd.edu/devhpcc/help/software.html#swcat_DataCompression |
| HACC cosmology simulation code                       | ECP Exasky project     | https://cosmology.alcf.anl.gov/                                         |
| RTM waveform simulation                              | ARAMCO                 | -                                                                       |
| XRHLIB (XHR file reader)                             | Alternative University | https://alternativeuniversity.net/compsci/raster/stor/xrhlib/           |
| HDF5 (H5Z-SZ filter)                                 | HDF5 group             | https://support.hdfgroup.org/HDF5/                                      |
| ADIOS2                                               | ORNL                   | https://github.com/ornladios/ADIOS2                                     |
-->

## Contact Us
In case of questions and comments or help, please contact the SZ team at [szlossycompressor@gmail.com](mailto:szlossycompressor@gmail.com).

## Acknowledgement
SZ is supported by the [Exascale Computing Project (ECP)](https://www.exascaleproject.org/), Project Number: 17-SC-20-SC, a collaborative effort of two DOE organizations – the Office of Science and the National Nuclear Security Administration, responsible for the planning and preparation of a capable exascale ecosystem. It is also supported by the National Science Foundation (NSF) under Grants [CCF-1617488](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1617488), [CCF-1619253](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1619253), [OAC-2003709](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2003709), [OAC-1948447/2034169](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2034169), and [OAC-2003624/2042084](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2042084).

![sz-acknowledgement](https://user-images.githubusercontent.com/5705572/93790911-6abd5980-fbe8-11ea-9c8d-c259260c6295.jpg)
