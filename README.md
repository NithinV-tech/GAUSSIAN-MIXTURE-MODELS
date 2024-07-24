# Background Subtraction using Gaussian Mixture Models (GMM)

This project implements a background subtraction algorithm using Gaussian Mixture Models (GMM) to separate foreground objects from the background in video frames. The implementation includes both a univariate and multivariate approach, with the latter recommended for better accuracy.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Tasks](#tasks)
- [Implementation](#implementation)
- [Results](#results)
- [Usage](#usage)
- [References](#references)

## Introduction

Background subtraction is a common computer vision task where the goal is to separate foreground objects from the background in a sequence of video frames. Gaussian Mixture Models (GMM) are employed to model the background and detect moving objects.

## Dataset

The dataset consists of a series of low-resolution camera footage frames. These frames are used for training the GMM and performing background subtraction.

## Tasks

### Part 1: Gaussian Mixture Models

1. **Implement GMM from Scratch**: Implement the GMM algorithm using multivariate Gaussian distributions. Optionally, the univariate version can also be implemented, but it may be less accurate.

### Part 2: Background Subtraction

1. **Frame Averaging**: Compute the average of every training frame to approximate the background image.
2. **GMM Per Pixel**: Maintain per-pixel GMMs with two components. Fit these GMMs using every training frame for the corresponding pixel and use them to predict pixel labels for subsequent frames.

## Implementation

### 1. Gaussian Mixture Models

- **Multivariate Gaussian Distributions**: Treat each pixel in an RGB image as a data point with [R, G, B] channels as the dimensions of the multivariate data point.
- **Univariate Gaussian Distributions**: Treat each value in the RGB image as an independent data point, which might lead to less accurate predictions.

### 2. Background Subtraction

#### Frame Averaging

- Compute the mean of every pixel across all training frames to get an approximate background image.

#### GMM Per Pixel

- Maintain a set of GMMs for each pixel.
- Fit these GMMs using the training frames.
- Use the GMMs to predict pixel labels for each subsequent frame.
- The Gaussian with the higher weight usually corresponds to the background.

### Class-Based Implementation

A class-based implementation of GMM is recommended to facilitate background subtraction. Refer to `sklearn.mixture.GaussianMixture` for ideas on structuring the class.

## Results

- **Frame Averaging Background Image**: Display the background image obtained by averaging the training frames.
- **GMM Background Image**: Display the background image obtained using GMM for each pixel.
- **Foreground Detection**: Display and save frames showing the foreground objects by subtracting the background.

## Usage

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/NithinV-tech/BACKGROUND-SUBTRACTION-GMM.git
   cd BACKGROUND-SUBTRACTION-GMM
