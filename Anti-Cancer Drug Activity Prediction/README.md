# Anti-Cancer Activity Prediction Project

## Overview

The Anti-Cancer Activity Prediction project focuses on bioassay tasks for predicting the anti-cancer activity of chemical compounds. Each compound is represented as a graph, with atoms as nodes and bonds as edges. The binary classification task involves determining whether a chemical compound is positive against non-small cell lung cancer or negative. This project leverages neural networks and model tuning to enhance predictive performance.

## Problem Formulation

### Input
- Chemical compounds represented as graphs with atoms (nodes) and bonds (edges).

### Output
- Binary classification: Positive (active against non-small cell lung cancer) or Negative.

### Data Mining Function
- Classification: Predicting the class label of chemical compounds.

### Challenges
- Graph representation: Handling graph-structured data adds complexity.
- Imbalanced dataset: The positive class samples are significantly fewer than the negative class.

### Impact
- Improved accuracy in predicting anti-cancer activity can aid drug discovery and development processes.

### Ideal Solution
- A robust model that effectively captures graph structure and handles class imbalance for accurate predictions.

  ## Model Tuning and Documentation

### Trial 0
- **Thoughts and Observations**: Initial model with default parameters.
- **Reasoning**: Establish baseline performance.
- **Outcome**: Moderate accuracy; underfitting observed.

### Trial 1
- **Thoughts and Observations**: Implementing Graph Convolutional Network (GCN) with basic aggregation mechanism.
- **Reasoning**: Evaluate basic GCN performance.
- **Outcome**: Improved training accuracy, but still underfitting.

### Trial 2
- **Thoughts and Observations**: Introducing a more advanced aggregation mechanism in GCN.
- **Reasoning**: Explore the impact of different message-passing mechanisms.
- **Outcome**: Enhanced training accuracy, slight improvement in validation set.

### Trial 3
- **Thoughts and Observations**: Experimenting with a different feature set.
- **Reasoning**: Assess the impact of feature engineering on model performance.
- **Outcome**: Incremental improvement in validation accuracy.

### Trial 4
- **Thoughts and Observations**: Adjusting graph data representation.
- **Reasoning**: Explore variations in graph representation.
- **Outcome**: Marginal improvement in validation accuracy.

### Trial 5
- **Thoughts and Observations**: Introducing up-sampling for positive class samples.
- **Reasoning**: Addressing class imbalance to enhance model's ability to learn from positive instances.
- **Outcome**: Improved precision for positive class but some overfitting.

### Trial 6
- **Thoughts and Observations**: Tuning hyperparameters for model optimization.
- **Reasoning**: Optimize model for better overall performance.
- **Outcome**: Reduced overfitting, improved validation accuracy.

### Trial 7
- **Thoughts and Observations**: Experimenting with a different graph convolution layer.
- **Reasoning**: Assess the impact of different convolutional layers on model learning.
- **Outcome**: Minimal change in performance.

### Trial 8
- **Thoughts and Observations**: Further hyperparameter tuning.
- **Reasoning**: Refine model configuration for optimal performance.
- **Outcome**: Improved overall accuracy and reduced overfitting.

### Trial 9
- **Thoughts and Observations**: Final model refinement with feature adjustments.
- **Reasoning**: Fine-tune feature selection for the best model.
- **Outcome**: Achieved better balance between precision and recall.

## Conclusion
The Anti-Cancer Activity Prediction project underwent an extensive tuning process to enhance model performance. Each trial involved thoughtful adjustments to features, hyperparameters, and model configurations. The documentation provides insights into the decision-making process, capturing the nuances of dealing with graph-structured data and addressing class imbalance. The ultimate goal is to contribute to the advancement of anti-cancer drug discovery through improved predictive modeling.

## Questions ❓
> 🌈 Based on the provided template, describe the format of the input file (sdf file).

* It's a chemical-data file formats that contains multiple records delimited by lines consisting of four dollar signs `$$$$`. It stores multiple molecules in a single file .It also store information about position of chemical compound atoms and the connections betwwen them.

* Each molecule starts with the name of the compound. Other sections includes information about Atom count, version number, edge connections.
- 1st block is atom block contains elements of the compound (nodes).
- 2nd block is bond block contains the bonds between atoms of the compound (edges).

> 🌈 What are the input tensors to the neural network model (their meaning, not just symbol)? What is each of their dims and their meaning (e.g. batch_size)?

The input tensors in this network are:

* data: It contains the tokenized chemical compound atoms(nodes). Each compound's nodes are retrieved, tokenized with the help of a tokenizer, and then padded using the pad_sequence technique. Each batch has the shape [batch_size*max_len_nodes], where `batch_size` denotes the number of samples in the batch and `max_len_nodes` denotes the length of tokenized nodes following padding.

* edge: It's the input tensor that contains information on atom connections. Edges have the shape [sum_of_all_edges,2]. The number of edges in each sample is represented by the total of all edges, or batch size.

* node2graph: This input tensor, which provides details about segmented ids, is used for segmented mean. Each batch has the shape [batch_size*max_len_nodes], where `batch_size` denotes the number of samples in the batch and `max_len_nodes` denotes the length of tokenized nodes following padding.

> 🌈 For each dim of gnn_out, what does it symbolize? For each dim of avg, what does it symbolize?

* gnn_out: The shape of the `gnn_out` is [batch_size_node_dimension,hidden layers], where `batch_size_node_dimension` is the dimension of the input data (node) vector (dimension of tokenized vector for the entire batch). It represents the model's aggregation output for each hidden layer.

* avg: Average computes the segmented mean of the `gnn_out` based on the segmented ids. The output of `gnn_out` for each sample in the `batch_size` is [tokenized_vector_dimension, hidden_layers]. Each sample has a unique segment id. Thus, `segment_mean` takes the mean of all the output data in the `gnn_out` output and represents one sample with one number for each hidden layer. The average tensor's final output is of the form [batch_size, hidden_layer]. It is a method of collecting information for each sample and presenting it as mean data.


> 🌈 What is the difference between segment_mean and tf.reduce_mean? For each dim of pred, what does it symbolize?

* segment_mean computes the mean of data with the same segmented ids.

* reduce_mean: computes the mean of a tensor's elements across dimensions given the parameters.
- To calculate the mean of tensor elements along various dimensions of the tensor, we used the TensorFlow reduce_mean method.

* pred: The final output (pred) indicates whether a chemical substance is active for cancer cells or not. Pred has the shape [batch_size,1]. Thus, the final output for each sample is a number that represents the probability of each chemical compound's activity.

> 🌈 What is the motivation/theory/idea to use multiple gcn layers comparing to just one? How many layers were used in the template?

* As Graph Convolutional Networks (GCNs) are a type of neural network that can operate on graph-structured data such as social networks or citation networks. By stacking multiple GCN layers, the information can be propagated across far reaches of a graph, which makes GCNs capable of learning from both content information as well as graph structure. In particular, GCN has a powerful ability to model higher-order neighborhood interactions by stacking multiple layers. Therefore, using multiple GCN layers can help capture more complex patterns in the data and improve the performance of the model.

* 4 layers were used in thr=e template
