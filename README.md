# Connectivities in Brain Network Activities
## Abstract
 Brain networks are invariably complex, share several common features with networks from other biological and physical systems, and may hence be characterized using complex systems methods. 

 The purpose of this project is to use dynamic modes decomposition(DMD) which is a powerful data-driven modeling method to construct the modes of brain activities during resting-state or task fMRI structure.
 
 ## Background
 I am Niloufar, a second-year M.Sc student in Computer Engineering at the University of Tehran, with a major in Computational Sciences and Algorithms. For my master thesis, I have focused on complex systems and  I am using dynamic mode decomposition on fMRI time series using open source databases like HCP. I chose a Computational Science major to develop stronger mathematical skills to deal with complex topics. 

In the past three years, I have focused on Data Science and Machine learning and worked on projects either with my advisor or during my internships which have helped me gain working experience in data collecting, data-driven modeling and analyzing to find appropriate patterns to help to make decisions on the different type of data sets, like signals, time-series images, clicking behaviors from online education platforms to music platform. 

## Introduction

The brain is a remarkably complex organ and understanding how networks of brain cells compute and function is a challenge as well. The brain is consists of an intricate, dynamic network of cells known as neurons. These neurons are tremendously heterogeneous in shape, function, and connectivity.

As in almost every other field of science and engineering, PCA and ICA widely used as a decomposition algorithm to analyze neural data in order to dimensionality reduction components of the high-dimensional data space.

Time-series data has the additional feature that snapshots of data are acquired in sequence in time, and methods that leverage this temporal relationship are often able to capture low-dimensional structures hidden from purely static methods. 

Dynamic mode decomposition (DMD), which is a powerful new technique for the discovery of dynamical systems from high-dimensional data. The growing success of DMD stems from the fact that it is an equation-free, data-driven method capable of providing an accurate decomposition of a complex system into spatiotemporal coherent structures.

In this project I will use DMD Algorithm to construct the modes of brain activities during resting-state.

## Data

Used data is from the Human Connectome Project(HCP) 7 Tesla fMRI dataset, mapping in 181 healthy young adults (1.6-mm resolution), which is the largest freely available collection of retinotopy data. We have selected the first eleven samples with the highest quality. 

## Preprocess
The atlas used on data is Harvard-Oxford atlas that it considers the probability distribution for each brain region, on display.
For preprocessing we used Nilearn which is a useful package for working with neuroimaging data.

In order to prepare the data with a format that is required for the DMD Algorithm matrices, converting the neuroimages data into a time series data structure is essential.

In the following, I will explain more about the Dynamic Mode Decomposition Method(DMD).

## What is Dynamic Mode Decomposition?

Dynamic mode decomposition is a powerful data-driven method to extract spatial-temporal coherent structures( DMD modes) from high dimensional data and give you a linear model for how those evolve in time.

DMD computes the leading eigendecomposition of the best-fit linear operator A relating the data X′ ≈ AX : 

![equation](http://latex.codecogs.com/png.latex?A%3DX%27%20X%5E%5Cdag)

(X is what we have about the system in m-1 snapshots, X' is the data of the system in next snapshot, A is an operator that helps to predict the behavior of the system)

The DMD modes, also called dynamic modes, are the eigenvectors of A and each DMD mode corresponds to a particular eigenvalue of A. 

## Dynamic Mode Decomposition Algorithm

The DMD Algorithm steps are as following:

1- Compute the SVD of X

![equation](http://latex.codecogs.com/png.latex?X%3DU%20%5CSigma%20V%5E%7B*%7D)

2- Compute Ã, the projection of the full matrix A onto U

![equation](http://latex.codecogs.com/gif.latex?%5Ctilde%7BA%7D%3DU%5E%7B*%7DAU%3DU%5E%7B*%7DX%27V%5CSigma%20%5E%7B-1%7D)

Step 3- Compute the eigenvalues and eigenvectors of Ã

![equation](http://latex.codecogs.com/png.latex?%5Ctilde%7BA%7DW%3DW%5CLambda)

Step 4- Reconstruct the eigendecomposition of A from calculated eigenvalues and eigenvectors

![equation](http://latex.codecogs.com/png.latex?A%20%5Cphi%20%3D%20%5Cphi%20%5CLambda%20%2C)

![equation](http://latex.codecogs.com/png.latex?%5Cphi%20%3D%20X%27%20V%20%5CSigma%5E%7B-1%7D%20W)
