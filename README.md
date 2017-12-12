# GPU-Cluster



## Introduction

Creating a GPU cluster with 20 computers connected over a Local Area Network (LAN).
While I am doing this for 20 computers this can be extended to more or less number of computers.



## OS & Hardware.

*Operating System*: Linux Ubuntu 17.04
*GPU*: Nvidia GeForce 730


## Basic Idea

We will create an MPI (Message Passing Interface) cluster and than access the GPU using the CPU cluster.
To read more about this technique read [here](https://developer.nvidia.com/mpi-solutions-gpus).


## Before Starting

We will first make sure everything is up-to-date.

open terminal and run the following command.

```bash

sudo apt-get update
sudo apt-get upgrade

```

Make sure all the PCs are connected to the internet and are in the LAN.


### *STEP 1:* Setting Up SSH.

We will first start by setting up SSH.
Doing this first is recommended so that all the further steps can be done remotely from a single PC.
[more](./1.Setting%20Up%20SSH/README.md)


### *STEP 2:* Setting Up MPI.

After setting up SSH we will go ahead and connect our CPUs.



### *STEP 3:* Setting up CUDA

Once MPI is setup let's see how we can use all the GPUs using this MPI cluster.



