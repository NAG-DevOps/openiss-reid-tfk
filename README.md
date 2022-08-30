# OpenISS Person Re-Identification Baseline
[![DOI](https://zenodo.org/badge/doi/10.5281/zenodo.5042265.svg)](https://doi.org/10.5281/zenodo.5042265)

This repo basically is the OpenISS re-implementation (tensorflow + keras) of a person
re-identification baseline proposed by the paper
["Bag of Tricks and A Strong Baseline for Deep Person Re-identification"](https://arxiv.org/abs/1903.07071).

The authors original implementation which is in Pytorch can be found in their
[repo](https://github.com/michuanhaohao/reid-strong-baseline).

This is a part of the Eric Lai's ML portion of the [OpenISS](https://github.com/OpenISS/OpenISS) project for his
master's thesis:

* [Haotao Lai](https://github.com/laihaotao), [*An OpenISS Framework Specialization for Person Re-identification*](https://spectrum.library.concordia.ca/985788/), Master's thesis, August 2019, Concordia University, Montreal

See also: [openiss-yolov3](https://github.com/OpenISS/openiss-yolov3).

## Environment

In our Speed cluster using GPUs, it could take up to 4 days to complete the training at 120 epochs.

TEST DATASET: Market1501

---- Train images: 12936

---- Query images: 3368

---- Gallery images: 15913

The pre-requisites to prepare the environment is located in `environment.yml`.

## Prepare 

Once logged into Speed, go to your speed-scratch directory:  `cd /speed-scratch/$USER/` and clone/download this git repository.

Before you run the script, you need to specify the dataset directory location. Go to the `reid.py` file,
check the global variable named `g_data_root`. If you don't have the dataset yet, you can get the dataset by
using the script in the `datasets` folder. If you do so, set `g_data_root = './datasets'`.

To download the test dataset go to:  `datasets/` and run `get_dataset_market1501.sh`

To train or try the model out, go to the very end of the `reid.py` file. Comment the method you don't want
and uncomment the method you want

*** IMPORTANT ***
Modify the script `openiss-2-speed.sh` to setup the job to be ready for CPUs or GPUs nodes; h_vmem= and gpu= CAN'T be enabled at the same time

## Run

On CPUs nodes: `qsub ./openiss-2-speed.sh`
On GPUs nodes: `qsub -q g.q ./openiss-2-speed.sh`

## Results
The result files are located in `output/cross_ds_v/`


## Theory

For the theory behind the code, please check with the wiki.
