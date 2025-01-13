# Generative Models and Sequence-to-Sequence Modeling with GANs, VAEs, and RNNs
 This project focuses on implementing Generative Adversarial Networks (GANs), Variational Autoencoders (VAEs), and Convolutional Autoencoders (CAEs) for image generation and reconstruction tasks. Additionally, RNNs are used for sequence modeling in a sequence-to-sequence problem, such as learning arithmetic operations from text and image data

# Generative Models and Sequence-to-Sequence Modeling with GANs, VAEs, and RNNs

This project focuses on implementing **Generative Adversarial Networks (GANs)**, **Variational Autoencoders (VAEs)**, and **Convolutional Autoencoders (CAEs)** for image generation and reconstruction tasks. Additionally, **Recurrent Neural Networks (RNNs)** are applied to sequence-to-sequence modeling for learning arithmetic operations across text and image modalities.

## Overview

### Task 1: Generative Modeling with CAEs, VAEs, and GANs
Generative models are used to learn the distribution of data and generate new, similar data. In this task, we will explore the following models:
1. **Convolutional Autoencoders (CAEs)**: Used for image compression and reconstruction.
2. **Variational Autoencoders (VAEs)**: A probabilistic extension of CAEs that enables image generation.
3. **Generative Adversarial Networks (GANs)**: Used for image generation through the adversarial training of a generator and a discriminator.

The dataset used is a **64x64 pixel facial dataset**, and the goal is to generate new images that resemble the input data.

### Task 2: Sequence-to-Sequence Modeling with Recurrent Neural Networks (RNNs)
RNNs are used for sequence-to-sequence tasks, specifically learning simple arithmetic operations:
1. **Text-to-Text Model**: Learn addition and subtraction operations from text-based arithmetic queries.
2. **Image-to-Text Model**: Learn arithmetic operations where the queries are represented as sequences of MNIST images.
3. **Text-to-Image Model**: Generate a sequence of images representing the answer to a text-based arithmetic query.

### Code Structure:
The project consists of a Jupyter notebook:
- **`GANs Generated Adversial Network Models.ipynb`**: The notebook contains the full implementation of generative modeling.
- **`RNNs Recurrent Neural ENtwork Models.ipynb`**: The notebook contains the full implementation of sequence-to-sequence tasks.


### Neural Network Architectures:

#### **Generative Models:**
1. **Convolutional Autoencoders (CAE)**:
   - Encoder: Convolutional layers with ReLU activation.
   - Decoder: Transposed convolutional layers with ReLU activation.
   - Loss: Mean Squared Error (MSE).
   
2. **Variational Autoencoders (VAE)**:
   - Encoder: Same as CAE but includes a probabilistic latent space.
   - Decoder: Same as CAE.
   - Loss: MSE + KL Divergence.

3. **Generative Adversarial Networks (GANs)**:
   - Generator: Uses transposed convolutional layers to generate images.
   - Discriminator: Classifies images as real or generated using convolutional layers.
   - Loss: Minimax loss function.

#### **Sequence-to-Sequence Models:**
1. **Text-to-Text**: A simple LSTM-based encoder-decoder model with one-hot encoding for input and output.
2. **Image-to-Text**: A model combining CNN and LSTM layers to extract features from images and predict corresponding arithmetic results in text form.
3. **Text-to-Image**: A text-to-image model using RNNs to generate images from a sequence of text-based arithmetic queries.

### Hyperparameters Table:

| Hyperparameter         | Values/Options                     |
|------------------------|-------------------------------------|
| **Optimizer**           | Adam (learning rate = 0.001)       |
| **Activation Function** | ReLU, Softmax, Tanh                |
| **Loss Function**       | MSE, Categorical Cross-Entropy     |
| **Batch Size**          | 32, 64, 128                        |
| **Epochs**              | 20-50                              |
| **Learning Rate**       | 0.001, 0.0001                      |
| **LSTM Units**          | 128, 256, 512                      |
| **Dropout Rate**        | 0.2, 0.5                           |

### Metrics Table:

| Metric                 | CAE            | VAE            | GAN            | Text-to-Text RNN | Image-to-Text RNN | Text-to-Image RNN |
|------------------------|----------------|----------------|----------------|------------------|-------------------|-------------------|
| **Training Accuracy**   | 94%            | 94%            | 85%            | 99.91%           | 71.48%            | 73.33%            |
| **Validation Accuracy** | 92%            | 92%            | 80%            | 99.90%           | 70.00%            | 74.82%            |
| **Test Accuracy**       | 92%            | 92%            | 78%            | 99.91%           | 72.42%            | 74.38%            |
| **Test Loss**           | 0.15           | 0.17           | 0.30           | 0.0034           | 1.5696            | 1.4310            |

### Output:

- **Task 1 Output** (Generative Models):
   - **CAE & VAE**: Sample reconstructions of input images.
   - **GAN**: Generated images at different epochs.
   - Visual inspection of the generated images shows a progression from noisy outputs to realistic images.

- **Task 2 Output** (RNN Models):
   - **Text-to-Text RNN**: Arithmetic answers predicted with 99.91% accuracy.
   - **Image-to-Text RNN**: Images representing arithmetic queries converted to text answers.
   - **Text-to-Image RNN**: Text queries converted into a sequence of images.

### Results & Discussion:
- **Generative Models**: The **VAE** and **GAN** models successfully generated realistic images, with **GANs** showing significant improvements in image quality across epochs. The **CAE** model performed well for image reconstruction.
- **RNN Models**: The **Text-to-Text RNN** model achieved near-perfect accuracy, while the **Image-to-Text** and **Text-to-Image** models demonstrated good generalization, though performance varied based on model complexity and hyperparameter tuning.

### Conclusion:
This project demonstrates the application of **CAE**, **VAE**, and **GANs** for image generation and reconstruction, and **RNNs** for sequence-to-sequence learning tasks such as arithmetic operations. The models performed well across both tasks, with GANs providing impressive image generation capabilities and RNNs achieving high accuracy in sequence modeling.

## References:
1. **GANs: Goodfellow et al. (2014)**: Generative Adversarial Nets.
2. **VAEs: Kingma & Welling (2014)**: Auto-Encoding Variational Bayes.
3. **RNNs: Hochreiter & Schmidhuber (1997)**: Long Short-Term Memory.

