# Anomaly Detection in Lorenz System using SINDy

This repository demonstrates how to use **Sparse Identification of Nonlinear Dynamics (SINDy)** for anomaly detection in time series data. We showcase this approach using the classic Lorenz system—a well-known model in fluid dynamics and chaos theory.

This notebook will:

- Simulate the Lorenz system over an extended period (0 to 40 seconds) to fully capture the butterfly attractor.
- Fit a SINDy model using the normal dynamics from the training data.
- Generate test data, where an anomaly is injected at a predetermined point.
- Compute the prediction error to detect anomalies.
- Generate plots that show:
    - The prediction error over time with an anomaly threshold.
    - 3D plots of the Lorenz attractor (normal training data) and the test data with the injected anomaly, along with a pointer indicating the anomaly.

## Table of Contents

- [Overview](#overview)
- [About SINDy](#about-sindy)
- [Benefits of SINDy for Anomaly Detection](#benefits-of-sindy-for-anomaly-detection)
- [Repository Contents](#repository-contents)

## Overview

This project simulates the Lorenz system over an extended time interval to capture the full butterfly attractor. A SINDy model is then fitted on the normal (training) data. By injecting an anomaly into a test dataset and comparing the model predictions against the actual data, we detect deviations that indicate an anomaly. The results are visualized with:
- A time series plot of the prediction error.
- Two 3D trajectory plots showing the normal Lorenz attractor and the perturbed (anomalous) trajectory, with an annotation pointing to the anomaly.

## About SINDy

**Sparse Identification of Nonlinear Dynamics (SINDy)** is a data-driven method that discovers the governing equations of a dynamical system from time series data. By selecting only the most significant terms from a large library of candidate functions, SINDy constructs a sparse, interpretable model that captures the essential dynamics of the system.

## Benefits of SINDy for Anomaly Detection

SINDy offers several key advantages over traditional anomaly detection methods in time series:

- **Interpretability:**  
  SINDy produces explicit mathematical equations representing the system's dynamics. This transparency allows for a better understanding of how the system operates and why an anomaly might have occurred.

- **Sparsity and Parsimony:**  
  By identifying only the most critical terms, SINDy avoids overfitting and yields a model that is both simple and robust. This simplicity makes it easier to detect deviations from normal behavior.

- **Early Anomaly Detection:**  
  Anomalies manifest as deviations from the normal dynamics captured by the SINDy model. By monitoring the prediction error (i.e., the difference between the observed data and the model's prediction), anomalies can be detected early and accurately.

## Repository Contents

- **`SINDy_for_anomaly_detection.ipynb`**  
  A Jupiter Notebook that:
  - Simulates the Lorenz system.
  - Fits a SINDy model on normal data.
  - Injects an anomaly into the test data.
  - Detects anomalies using prediction errors.
  - Visualizes the results with both time series and 3D plots (including a pointer to the anomaly).

- **`README.md`**  
  This file.

## Installation

Ensure you have Python 3 installed. Then, install the required Python packages using pip:

```bash
pip install numpy pysindy matplotlib scipy
