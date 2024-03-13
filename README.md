# Practical Work about Kalman Filtering

## Overview
The project includes a comprehensive Jupyter notebook that details the implementation and conceptual background of the Kalman Filter, a Python script for robot simulation, and related data and license files.

Kalman Filtering is a powerful algorithm used for estimating the state of a linear dynamic system from a series of noisy measurements. It is widely applied in various fields such as robotics, aerospace, finance, and more. This project specifically explores its application in robot navigation and simulation.

## Theoretical Background
The Kalman Filter is an algorithm that provides an efficient computational means to estimate the state of a process, in a way that minimizes the mean of the squared error. It operates recursively on streams of noisy input data to produce a statistically optimal estimate of the underlying system state.

Given a linear dynamic system modeled as:

- **State Equation**: $$x_{k} = Ax_{k-1} + Bu_{k} + w_{k-1}$$
- **Measurement Equation**: $$z_{k} = Hx_{k} + v_{k}$$

where:
- $x_k$ is the state at time $k$,
- $A$ is the state transition matrix,
- $B$ is the control input matrix,
- $u_k$ is the control input at time $k$,
- $w_k$ is the process noise,
- $z_k$ is the measurement at time $k$,
- $H$ is the observation matrix,
- $v_k$ is the measurement noise.

The Kalman Filter estimates the state $x_k$ from the measurements $z_k$ by computing a series of steps, namely the *Prediction* and *Update* steps. The key equations for these steps are:

- **Prediction**:
    - Predicted State Estimate: $$\hat{x} _ {k|k-1} = A\hat{x} _ {k-1|k-1} + Bu_{k}$$
    - Predicted Covariance Estimate: $$P_{k|k-1} = AP_{k-1|k-1}A^T + Q$$
- **Update**:
    - Kalman Gain: $$K_k = P_{k|k-1}H^T(HP_{k|k-1}H^T + R)^{-1}$$
    - Updated State Estimate: $$\hat{x}_ {k|k} = \hat{x}_ {k|k-1} + K_k(z_k - H\hat{x}_{k|k-1})$$
    - Updated Covariance Estimate: $$P_{k|k} = (I - K_kH)P_{k|k-1}$$

These equations form the basis of the Kalman Filter, enabling it to estimate the state of a dynamic system in a way that is optimal under the assumption of Gaussian errors.

## Contents
- `TP_KalmanFiltering_Daniel-Torres_Laura-Castaneda.ipynb`: The main Jupyter notebook containing the project's code, explanations, and results. It provides a detailed walkthrough of implementing the Kalman Filter, including theoretical concepts and practical examples.
- `robot_simulation.py`: A Python script used to simulate a robot's movements. This script serves as a practical demonstration of applying the Kalman Filter in a dynamic system.
- `data`: A directory containing data files used in the notebook for demonstration purposes.
- `licenses`: A directory with license files for the project and any dependencies.

## Getting Started
To get started with this project, clone this repository and ensure you have Jupyter Notebook installed. You can run the notebook by navigating to the repository's directory and launching Jupyter Notebook:

jupyter notebook TP_KalmanFiltering_Daniel-Torres_Laura-Castaneda.ipynb

## Prerequisites
Make sure you have the following Python packages installed:
- numpy
- matplotlib
- scipy

These can be installed using pip:

`pip install numpy matplotlib scipy`
