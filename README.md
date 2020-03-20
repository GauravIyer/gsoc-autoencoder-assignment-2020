# Evaluative Task for ATLAS, under GSoC 2020 

## Problem Statement
The task consisted of compressing data related to jet events with 4 variables (**m**, **pt**, **phi**, and **eta**) down to 3 variables using an autoencoder.

## Repository Structure
One simply needs to run all the cell blocks in the Jupyter notebook titled "HEPAutoencoder.ipynb". Please note that the project was created using Google Colab, so there may be some boilerplate code that may not compile locally.

The various plots have been saved in the folder titled **Graphs** .

## Approach
The raw data was put into Pandas dataframes for a glimpse into its structure, and was then standardised to center it about 0 mean and unit variance.

The architecture used was the same as in the reference project and thesis by Mr. Eric Wulff, with minor adjustments. The tanh activations were replaced by **Leaky ReLUs**, and the number of nodes per layer were increased slightly, mostly to match with convention.

## Hyperparameters
Batch size: 64 (chosen arbitrarily, with the upside that lower batch sizes give more accurate loss curves).

Optimizer: Adam with a leaerning rate scheduler starting at 1e-3 and decreased by a factor of 10 at certain checkpoints during training.

Loss Function: Mean Squared Error.

