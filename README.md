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

A powerful GPU is required for running the code, with Nivida GTX 1070ti, a training with the standard 120 epochs will take almost 4 hours.

This implementatoin is based on tensorflow and keras (currently not other backend are suppoted rather than tf).

The pre-requisites to prepare the environment are located in `environment.yml`.

We suggest you to run the script in any Python virtual environment and install the packages versions as described in `environment.yml`.

## Run

Before you run the script, you need to specify the dataset directory location. Go to the `reid.py` file,
check the global variable named `g_data_root`. If you don't have the dataset yet, you can get the dataset by
using the script in the `datasets` folder. If you do so, set `g_data_root = './datasets'`.

To download the test dataset go to:  `datasets/` and run `get_dataset_market1501.sh`

To train or try the model out, go to the very end of the `reid.py` file. Comment the method you don't want
and uncomment the method you want and run:

```
python reid.py
```

## Results
The result files are located in `output/cross_ds_v/`


## Theory

For the theory behind the code, please check with the wiki.

## Configuration on Conda Virtual Environment
- Conda/anaconda must be installed in your system
- Clone this repo
- To download the dataset go to:  datasets/ and run get_dataset_market1501.sh
- In reid.py set the epochs (g_epochs=120 by default)
- To create the environment: conda env create -f environment.yml -p /your_path/name_of_environment
- Run conda activate /your_path/name_of_environment
- Run python reid.py to execute the program
- once finished: conda deactivate
- To remove remove environment: conda env remove -p /your_path/name_of_environment
