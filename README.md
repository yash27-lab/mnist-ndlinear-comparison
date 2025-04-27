# Replacing Standard Linear Layers with NdLinear on MNIST Classification

## Overview
This project explores the impact of replacing traditional `nn.Linear` layers with the innovative `NdLinear` layer in a convolutional neural network (CNN) trained for handwritten digit recognition. NdLinear preserves multi-dimensional tensor structures, potentially improving parameter efficiency and expressiveness without compromising performance.

## Why MNIST?
The MNIST dataset was chosen as it serves as a globally recognized benchmark for evaluating novel architectures in machine learning. Its manageable complexity and standardization provide an ideal environment to rapidly validate and benchmark architectural innovations like NdLinear without the computational overhead of large-scale datasets. MNIST ensures that any architectural changes are directly attributable to model design rather than dataset intricacies.

## Project Structure
- **CNN_Normal:** A baseline CNN architecture using traditional `nn.Linear` layers after convolutional operations.
- **CNN_NdLinear:** An identical CNN backbone where `nn.Linear` layers are replaced with `NdLinear`, preserving spatial tensor structure.

Both models were trained on the MNIST dataset for 10 epochs, and performance metrics were evaluated in terms of training loss and validation accuracy.

## Results

| Metric | CNN_Normal (nn.Linear) | CNN_NdLinear |
|:---|:---|:---|
| Final Training Loss (Epoch 10) | 0.0041 | 0.0769 |
| Validation Accuracy | 98.67% | 98.07% |
| Parameter Efficiency | Standard | More compact |

- **CNN_Normal** achieved a slightly higher final accuracy (98.67%), reflecting the traditional architecture's optimization for MNIST.
- **CNN_NdLinear** achieved an impressive 98.07% accuracy while being more parameter-efficient and preserving the tensor's multi-dimensional structure.
- **Convergence Pattern:** NdLinear exhibited faster convergence during early epochs, closing the performance gap effectively as training progressed.

## Key Takeaways
- NdLinear offers a compelling alternative to conventional linear layers, achieving near-equivalent accuracy with improved model compactness.
- The preservation of multi-dimensional tensor structure can be critical for scaling models to more complex domains, such as vision transformers and multimodal architectures.
- The study successfully validates the hypothesis that NdLinear can serve as an efficient, scalable replacement in deep learning architectures.

## How to Run
1. Clone the repository or open the provided Colab notebook.
2. Install NdLinear:
   ```bash
   !git clone https://github.com/ensemble-core/NdLinear.git
   %cd NdLinear
   !pip install .
   %cd ..
