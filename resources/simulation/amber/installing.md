---
layout: post
title: Installing Amber20
description: Notes on Installing Amber20 on Ubuntu Desktop
---

Make sure you have the following installed! [Amber Installation](https://ambermd.org/InstUbuntu.php)

apt -y update
apt -y install tcsh make \
               gcc gfortran \
               flex bison patch bc wget \
               xorg-dev libz-dev libbz2-dev \
               readline-doc libboost-all-dev \
               libblas-dev liblapack-dev

If you want to install Amber in parallel, you can use OpenMPI through:

apt -y install openmpi-bin libopenmpi-dev openssh-client

In your Programs/sources/ folder, untar the files:

tar xvjf AmberTools20.tar.bz2
tar xvjf Amber20.tar.bz2

cd into amber20_src/build 

Modify the run_cmake script with the following flags:

cmake $AMBER_PREFIX/amber20_src \
    -DCMAKE_INSTALL_PREFIX=/home/van/Programs/amber20 \
    -DCOMPILER=GNU  \
    -DMPI=FALSE -DCUDA=FALSE -DINSTALL_TESTS=TRUE \
    -DDOWNLOAD_MINICONDA=FALSE -DMINICONDA_USE_PY3=TRUE \
    -DDISABLE_TOOLS='cpptraj;mdgx' -DTRUST_SYSTEM_LIBS=TRUE \
    -DPRINT_PACKAGING_REPORT=TRUE \
    2>&1 | tee  cmake.log

Then run the following to install Amber CPU:

./run_cmake
make install 
source /home/van/Programs/amber20/amber.sh

After successful installation, run serial test before moving on:

cd $AMBERHOME
make test.serial

### Parallel Installation

cd /home/van/Programs/sources/amber20_src/build

Modify the run_cmake script to set:

-DMPI=TRUE

Then run the following to install Amber MPI:

./run_cmake
make install -j 2
source /home/van/Programs/amber20/amber.sh

After successful installation, run parallel test before moving on:

cd $AMBERHOME
export DO_PARALLEL="mpirun -np 4"
make test.parallel

### GPU Installation

cd /home/van/Programs/sources/amber20_src/build

Modify the run_cmake script to set:

-DCUDA=TRUE

Then run the following to install Amber MPI:

./run_cmake
make install -j 2
source /home/van/Programs/amber20/amber.sh


