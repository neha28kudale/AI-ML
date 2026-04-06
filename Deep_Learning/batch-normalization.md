# Batch Normalization in Deep Learning

## Introduction

Batch Normalization is a technique used in deep neural networks to make training faster and more stable. It was introduced to address the problem of changing data distributions inside a network during training.

In simple terms, it normalizes the inputs of each layer so that the model can learn more efficiently.

---

## Why Batch Normalization is Needed

When training deep networks, the distribution of inputs to each layer keeps changing as the parameters of the previous layers update. This is often referred to as *internal covariate shift*.

Because of this:
- Training becomes slow
- The model becomes sensitive to weight initialization
- Learning becomes unstable in deeper networks

Batch Normalization helps reduce these issues by keeping the input distribution more consistent.

---

## How Batch Normalization Works

Batch Normalization operates on mini-batches of data. For each feature in a layer, it performs the following steps:

1. Compute the mean of the batch  
2. Compute the variance of the batch  
3. Normalize the data  
4. Scale and shift the normalized values  

### Step-by-step explanation

Let the input be x.

- Mean:
  
  μ = (1 / N) * Σx

- Variance:
  
  σ² = (1 / N) * Σ(x − μ)²

- Normalization:
  
  x̂ = (x − μ) / √(σ² + ε)

- Scale and shift:
  
  y = γx̂ + β

Here:
- γ (gamma) is a learnable scaling parameter  
- β (beta) is a learnable shifting parameter  
- ε is a small constant to avoid division by zero  

This ensures the normalized data can still represent the required distribution.

---

## Where Batch Normalization is Used

Batch Normalization is commonly used in:
- Convolutional Neural Networks (CNNs)
- Fully connected deep neural networks
- Modern architectures like ResNet

It is usually applied after the linear transformation and before the activation function.

---

## Advantages of Batch Normalization

- Speeds up training significantly  
- Allows the use of higher learning rates  
- Reduces sensitivity to initialization  
- Provides slight regularization, reducing overfitting  
- Helps in training deeper networks  

---

## Limitations of Batch Normalization

- Performance depends on batch size (not ideal for very small batches)  
- Adds extra computation during training  
- Behavior differs during training and inference  
- Not always suitable for sequential models like RNNs  

---

## Batch Normalization vs Layer Normalization

*Batch Normalization
  Normalizes data across the entire batch
  Depends on batch size for performance
  Works best for CNNs and large batch training
*Layer Normalization
  Normalizes data across features within a single sample
  Does not depend on batch size
  Works well for RNNs and transformer models

---

## Intuition Behind Batch Normalization

You can think of Batch Normalization as standardizing data at every layer, similar to how input data is normalized before training.

Instead of letting each layer deal with constantly shifting data, Batch Normalization ensures that the inputs remain in a stable range. This makes learning easier and more predictable.

---

## Conclusion

Batch Normalization is a simple yet powerful technique that improves the performance and stability of deep neural networks. It has become a standard component in many modern architectures due to its ability to accelerate training and improve generalization.

---

## Key Takeaways

- Normalizes inputs of each layer  
- Reduces internal covariate shift  
- Speeds up training and improves stability  
- Works best with sufficiently large batch sizes  
