# Bayesian Network for Pipe Leak Detection
This project aims to detect pipe leaks using a Bayesian Network built from pressure sensor data. Bayesian Networks are probabilistic graphical models that represent a set of variables and their conditional dependencies via a directed acyclic graph (DAG). This approach allows us to model the relationship between pressure sensors and the likelihood of a pipe leak.

## Overview
A Bayesian Network is constructed using pgmpy, a Python library for working with probabilistic graphical models. The network structure consists of two pressure sensors (PS1 and PS2) as parent nodes and a leak node (Leak) as the child node. The project involves the following steps:

### Data Preparation:

Load the dataset containing pressure sensor readings and leak status.
Calculate the probability distributions for each pressure sensor and the conditional probabilities for leaks given the sensor readings.
Bayesian Network Construction:

### Define the structure of the network.

Create Conditional Probability Distributions (CPDs) for each node based on the dataset.
Add these CPDs to the Bayesian Network model.
Verify the model to ensure consistency and correctness.

### Inference:

Use the Variable Elimination algorithm to perform inference on the network.
Query the network to determine the probability of a pipe leak given specific sensor readings.
Detailed Steps
Loading Data:

The dataset, typically in CSV format, is loaded into a pandas DataFrame. This dataset contains columns for the pressure sensor readings (PS1 and PS2) and the leak status (Leak).
Defining Network Structure:

The structure of the Bayesian Network is defined with two parent nodes (PS1 and PS2) and one child node (Leak). This structure reflects the assumption that the leak status depends on the readings from both pressure sensors.

### Calculating CPDs:

For each pressure sensor, a CPD is calculated. This represents the probability distribution of the sensor's readings.
For the leak node, a conditional CPD is calculated. This represents the probability of a leak given the readings from both pressure sensors. The values are derived from the dataset by grouping data and normalizing leak counts.
Adding CPDs to the Model:

The calculated CPDs are added to the Bayesian Network model. This step ensures the network is equipped with the necessary probabilistic information.

### Model Verification:

The network model is checked for consistency using an assertion. This step ensures that all CPDs are correctly defined and compatible with the network structure.
Inference:

Variable Elimination is used for inference in the Bayesian Network. This algorithm allows querying the network to find the probability of specific outcomes.
In this project, the network is queried to determine the probability of a pipe leak given specific readings from the pressure sensors.
Result Interpretation:

The result of the inference is a probability distribution over the leak node, given the evidence from the pressure sensors. This provides the likelihood of a pipe leak under the specified conditions.

### Usage
To use this code:

Ensure the required libraries (pgmpy, pandas, and numpy) are installed.
Load your dataset, replacing 'pipe leak-dataset.csv' with the path to your file.
Run the script to build the Bayesian Network and perform inference.
The Bayesian Network model is a powerful tool for detecting pipe leaks, leveraging probabilistic reasoning to infer the likelihood of leaks based on sensor data. This approach can be extended to include more sensors and additional variables, providing a robust framework for various leak detection applications.
