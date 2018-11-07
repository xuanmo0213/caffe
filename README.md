# Caffe
[![Build Status](https://travis-ci.org/BVLC/caffe.svg?branch=master)](https://travis-ci.org/BVLC/caffe)
[![License](https://img.shields.io/badge/license-BSD-blue.svg)](LICENSE)

Caffe is a deep learning framework made with expression, speed, and modularity in mind.
It is developed by the Berkeley Vision and Learning Center ([BVLC](http://bvlc.eecs.berkeley.edu)) and community contributors.

Check out the [project site](http://caffe.berkeleyvision.org) for all the details like
- [DIY Deep Learning for Vision with Caffe](https://docs.google.com/presentation/d/1UeKXVgRvvxg9OUdh_UiC5G71UMscNPlvArsWER41PsU/edit#slide=id.p)
- [Tutorial Documentation](http://caffe.berkeleyvision.org/tutorial/)
- [BVLC reference models](http://caffe.berkeleyvision.org/model_zoo.html) and the [community model zoo](https://github.com/BVLC/caffe/wiki/Model-Zoo)
- [Installation instructions](https://github.com/intel/caffe/wiki/Installation)

and step-by-step examples.

[![Join the chat at https://gitter.im/BVLC/caffe](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/BVLC/caffe?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Please join the [caffe-users group](https://groups.google.com/forum/#!forum/caffe-users) or [gitter chat](https://gitter.im/BVLC/caffe) to ask questions and talk about methods and models.
Framework development discussions and thorough bug reports are collected on [Issues](https://github.com/BVLC/caffe/issues).

Happy brewing!


# SSD: Single Shot MultiBox Detector
This repository contains merged code issued as pull request to BVLC caffe written by:
[Wei Liu](http://www.cs.unc.edu/~wliu/), [Dragomir Anguelov](https://www.linkedin.com/in/dragomiranguelov), [Dumitru Erhan](http://research.google.com/pubs/DumitruErhan.html), [Christian Szegedy](http://research.google.com/pubs/ChristianSzegedy.html), [Scott Reed](http://www-personal.umich.edu/~reedscot/), [Cheng-Yang Fu](http://www.cs.unc.edu/~cyfu/), [Alexander C. Berg](http://acberg.com).

Original branch can be found at https://github.com/weiliu89/caffe/tree/ssd.

Read our [wiki page](https://github.com/intel/caffe/wiki/SSD:-Single-Shot-MultiBox-Detector) for more details.

# PFF Caffe
**This is an experimental　branch maintained by Jingjing Zhu (@xuanmo0213). It is still in progress.**

This fork is dedicated to provide a common platform for all pff caffe programs, including arm platform support, memory optimization, and custom layers.

## Building
Build procedure is basically the same as on bvlc-caffe-master branch. Here are some steps to follow:

### Prerequisites
This caffe is supported on Linux distributions that use gcc with c++11 support.

Some general dependencies can be installed by following command.
```
sudo apt-get install libprotobuf-dev libleveldb-dev libsnappy-dev libopencv-dev libhdf5-serial-dev protobuf-compiler
sudo apt-get install --no-install-recommends libboost-all-dev
sudo apt-get install libopenblas-dev libtcmalloc_minimal4
```

*CUDA*: The package is default to compile with CUDA. Install the NVIDIA package manually. A NVIDIA developer account is needed to access.
If you want to compile with CUDA support, install
- [NVIDIA CUDA](https://developer.nvidia.com/cuda-downloads) 8.0 suggested
- [NVIDIA cuDNN](https://developer.nvidia.com/cudnn) version according to CUDA installed

*BLAS*: install ATLAS by `sudo apt-get install libatlas-base-dev` or install OpenBLAS by `sudo apt-get install libopenblas-dev` or MKL for better CPU performance. The default build is with OpenBLAS, change Makefile.config if you want to build with ATLAS.

*Python (optional)*: if you use the default Python you will need to `sudo apt-get install the python-dev package` to have the Python headers for building the pycaffe interface.

### Installing the caffe
A default Makefile.config already included for suggested building dependencies.

To build the caffe, simple running
```
make -j8
```
### Running the tests
If a runtest is preferred, simple run
```
make runtest
```

## License
Caffe is released under the BSD license. The BVLC reference models are released for unrestricted use.
