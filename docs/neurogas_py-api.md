---
weight: 11
title: neurogas
---




## Table of Contents

- 🅼 [neurogas](#neurogas)

<a name="neurogas"></a>
## 🅼 neurogas

- **Classes:**
  - 🅲 [Gng](#neurogas-Gng)

### Classes

<a name="neurogas-Gng"></a>
### 🅲 neurogas\.Gng

```python
class Gng:
```

**Functions:**

<a name="neurogas-Gng-__new__"></a>
#### 🅵 neurogas\.Gng\.\_\_new\_\_

```python
def __new__() -> Gng:
```

Python constructor: \`Gng\(\)\`
<a name="neurogas-Gng-fit"></a>
#### 🅵 neurogas\.Gng\.fit

```python
def fit() -> None:
```

Runs the complete training process until maximum epochs are reached\.

This function manages the full training loop by iterating through epochs and samples
until the maximum number of epochs is reached or the target error is achieved\.
<a name="neurogas-Gng-fit_step"></a>
#### 🅵 neurogas\.Gng\.fit\_step

```python
def fit_step() -> None:
```

Executes a single fitting iteration \(one epoch\)\.

This function performs one complete training epoch by processing all samples in
the dataset and updating the network structure accordingly\.
<a name="neurogas-Gng-get_edges"></a>
#### 🅵 neurogas\.Gng\.get\_edges

```python
def get_edges() -> list[tuple[int, int]]:
```

Returns the current edges as \(from, to\) pairs\.

Each tuple represents a directed edge between two neurons\.

\# Returns

A vector of tuples where each tuple contains \(from\_neuron\_id, to\_neuron\_id\)
<a name="neurogas-Gng-get_model_string"></a>
#### 🅵 neurogas\.Gng\.get\_model\_string

```python
def get_model_string() -> str:
```

Returns the current model as a JSON string\.

This function serializes all neurons and edges in the network to a JSON format
without writing to a file, useful for immediate processing or transmission\.

\# Returns

A String containing the serialized model in JSON format
<a name="neurogas-Gng-get_neurons"></a>
#### 🅵 neurogas\.Gng\.get\_neurons

```python
def get_neurons() -> list[tuple[int, list[float]]]:
```

Returns the current neurons as \(id, position\) pairs\.

The positions are vectors stored as f64 arrays\.

\# Returns

A vector of tuples where each tuple contains \(neuron\_id, neuron\_position\)
<a name="neurogas-Gng-init_dataset"></a>
#### 🅵 neurogas\.Gng\.init\_dataset

```python
def init_dataset(filename_dataset: str) -> None:
```

Initializes the dataset from a CSV file\.

This function loads sample data from a CSV file and prepares it for training,
using the configured input width to properly parse each sample\.

\# Arguments

\* \`filename\_dataset\` - The path to the CSV dataset file
<a name="neurogas-Gng-init_dataset_vec"></a>
#### 🅵 neurogas\.Gng\.init\_dataset\_vec

```python
def init_dataset_vec(data: Sequence[float]) -> None:
```

Initializes the dataset from a vector of f64 values\.

This function loads sample data directly from a vector and prepares it for training,
using the configured input width to properly parse each sample\.

\# Arguments

\* \`data\` - A vector of f64 values representing the dataset samples
<a name="neurogas-Gng-init_step"></a>
#### 🅵 neurogas\.Gng\.init\_step

```python
def init_step() -> None:
```

Initializes the training process for a single epoch\.

This function prepares the system for training by setting up initial state and
preparing for the first epoch of training\.
<a name="neurogas-Gng-load_config"></a>
#### 🅵 neurogas\.Gng\.load\_config

```python
def load_config(filename_config: str) -> None:
```

Loads a configuration file into the GNG system\.
<a name="neurogas-Gng-save_model_json"></a>
#### 🅵 neurogas\.Gng\.save\_model\_json

```python
def save_model_json(filename_output: str) -> None:
```

Exports the current model to a JSON file\.

This function serializes all neurons and edges in the network to a structured JSON format
that can be saved to disk for later loading or analysis\.

\# Arguments

\* \`filename\_output\` - The path where the JSON file will be written
<a name="neurogas-Gng-set_parameters"></a>
#### 🅵 neurogas\.Gng\.set\_parameters

```python
def set_parameters(input_width: int, weight_rng_min: float, weight_rng_max: float, edge_removal_age: int, neuron_creation_interval: int, max_epochs: int, max_neurons: int, target_error: float, epsilon_w: float, epsilon_n: float, alpha: float, beta: float, rng_seed: int) -> None:
```

Sets all model parameters directly\.

This function provides a programmatic way to configure all GNG system parameters
without requiring a configuration file\.

\# Arguments

\* \`input\_width\` - The dimensionality of input samples
\* \`weight\_rng\_min\` - Minimum value for initial weight randomization
\* \`weight\_rng\_max\` - Maximum value for initial weight randomization
\* \`edge\_removal\_age\` - Age threshold for edge removal
\* \`neuron\_creation\_interval\` - Iteration interval between neuron creation
\* \`max\_epochs\` - Maximum number of training epochs
\* \`max\_neurons\` - Maximum number of neurons allowed in the network
\* \`target\_error\` - Target error level for termination
\* \`epsilon\_w\` - Weight update parameter for winner neuron
\* \`epsilon\_n\` - Weight update parameter for neighbor neurons
\* \`alpha\` - Error decay factor for newly created neurons
\* \`beta\` - Global error decay factor
\* \`rng\_seed\` - Random number generator seed for reproducibility

<a name="neurogas-exports"></a>
### Exports

- 🅼 [`Gng`](#neurogas-Gng)
