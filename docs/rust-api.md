
---
weight: 11
title: neurogas
---



A Rust implementation of the Growing Neural Gas (GNG) algorithm for unsupervised learning.

## Table of Contents

- 🅼 [gng](#gng)


<a name="gng"></a>
## 🅼 gng

This module provides a complete implementation of the GNG algorithm with support for
training, model persistence, and various utility functions for managing neural networks.


### Structs

<a name="gng-Gng"></a>
### 🅲 gng\.Gng

```rust
pub struct Gng {
    // fields are private
}
```

A wrapper struct for the GNG system that provides a clean API for users.

This struct encapsulates the internal `Gng_System` and provides a simplified
interface for common operations like training, configuration, and model management.

**Implements:** `Default`

**Functions:**

<a name="gng-Gng-new"></a>
#### 🅵 gng\.Gng::new

```rust
pub fn new() -> Self
```

Creates a new GNG instance with default settings.

**Returns**

A new `Gng` instance initialized with default parameters.
<a name="gng-Gng-fit"></a>
#### 🅵 gng\.Gng::fit

```rust
pub fn fit(&mut self)
```

Runs the complete training process until maximum epochs are reached.

This function manages the full training loop by iterating through epochs and samples
until the maximum number of epochs is reached or the target error is achieved.
<a name="gng-Gng-fit_step"></a>
#### 🅵 gng\.Gng::fit\_step

```rust
pub fn fit_step(&mut self)
```

Executes a single fitting iteration (one epoch).

This function performs one complete training epoch by processing all samples in
the dataset and updating the network structure accordingly.
<a name="gng-Gng-get_edges"></a>
#### 🅵 gng\.Gng::get\_edges

```rust
pub fn get_edges(&mut self) -> Vec<(usize, usize)>
```

Returns the current edges as (from, to) pairs.

Each tuple represents a directed edge between two neurons.

**Returns**

A vector of tuples where each tuple contains (from\_neuron\_id, to\_neuron\_id).
<a name="gng-Gng-get_model_string"></a>
#### 🅵 gng\.Gng::get\_model\_string

```rust
pub fn get_model_string(&mut self) -> String
```

Returns the current model as a JSON string.

This function serializes all neurons and edges in the network to a JSON format
without writing to a file, useful for immediate processing or transmission.

**Returns**

A `String` containing the serialized model in JSON format.
<a name="gng-Gng-get_neurons"></a>
#### 🅵 gng\.Gng::get\_neurons

```rust
pub fn get_neurons(&mut self) -> Vec<(usize, Vec<f64>)>
```

Returns the current neurons as (id, position) pairs.

The positions are vectors stored as f64 arrays.

**Returns**

A vector of tuples where each tuple contains (neuron\_id, neuron\_position).
<a name="gng-Gng-init_dataset"></a>
#### 🅵 gng\.Gng::init\_dataset

```rust
pub fn init_dataset(&mut self, filename_dataset: &str)
```

Initializes the dataset from a CSV file.

This function loads sample data from a CSV file and prepares it for training,
using the configured input width to properly parse each sample.

**Arguments**

- `filename_dataset` – The path to the CSV dataset file.
<a name="gng-Gng-init_dataset_vec"></a>
#### 🅵 gng\.Gng::init\_dataset\_vec

```rust
pub fn init_dataset_vec(&mut self, data: &Vec<f64>)
```

Initializes the dataset from a vector of f64 values.

This function loads sample data directly from a vector and prepares it for training,
using the configured input width to properly parse each sample.

**Arguments**

- `data` – A vector of f64 values representing the dataset samples.
<a name="gng-Gng-init_step"></a>
#### 🅵 gng\.Gng::init\_step

```rust
pub fn init_step(&mut self)
```

Initializes the training process for a single epoch.

This function prepares the system for training by setting up initial state and
preparing for the first epoch of training.
<a name="gng-Gng-load_config"></a>
#### 🅵 gng\.Gng::load\_config

```rust
pub fn load_config(&mut self, filename_config: &str)
```

Loads configuration parameters from a JSON file.

This function reads configuration values such as input width, weight range,
and training parameters from a JSON file to initialize the GNG system.

**Arguments**

- `filename_config` – The path to the JSON configuration file.
<a name="gng-Gng-save_model_json"></a>
#### 🅵 gng\.Gng::save\_model\_json

```rust
pub fn save_model_json(&mut self, filename_output: &str)
```

Exports the current model to a JSON file.

This function serializes all neurons and edges in the network to a structured JSON format
that can be saved to disk for later loading or analysis.

**Arguments**

- `filename_output` – The path where the JSON file will be written.
<a name="gng-Gng-set_parameters"></a>
#### 🅵 gng\.Gng::set\_parameters

```rust
pub fn set_parameters(
    &mut self,
    input_width: usize,
    weight_rng_min: f64,
    weight_rng_max: f64,
    edge_removal_age: usize,
    neuron_creation_interval: usize,
    max_epochs: usize,
    max_neurons: usize,
    target_error: f64,
    epsilon_w: f64,
    epsilon_n: f64,
    alpha: f64,
    beta: f64,
    rng_seed: u64,
)
```

Sets all model parameters directly.

This function provides a programmatic way to configure all GNG system parameters
without requiring a configuration file.

**Arguments**

- `input_width` – The dimensionality of input samples.
- `weight_rng_min` – Minimum value for initial weight randomization.
- `weight_rng_max` – Maximum value for initial weight randomization.
- `edge_removal_age` – Age threshold for edge removal.
- `neuron_creation_interval` – Iteration interval between neuron creation.
- `max_epochs` – Maximum number of training epochs.
- `max_neurons` – Maximum number of neurons allowed in the network.
- `target_error` – Target error level for termination.
- `epsilon_w` – Weight update parameter for winner neuron.
- `epsilon_n` – Weight update parameter for neighbor neurons.
- `alpha` – Error decay factor for newly created neurons.
- `beta` – Global error decay factor.
- `rng_seed` – Random number generator seed for reproducibility.

<a name="gng-exports"></a>
### Exports

- 🅲 [`Gng`](#gng-Gng)


