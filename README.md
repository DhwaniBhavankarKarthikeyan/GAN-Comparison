# GAN Evaluation using ChestMNIST Dataset

This project implements Generative Adversarial Networks (GANs) to generate synthetic medical images using the ChestMNIST dataset. The evaluation includes metrics such as Inception Score (IS), Fréchet Inception Distance (FID), and visual inspection.

## Overview
The goal of this project is to experiment with different GAN architectures and evaluate their performance on medical image synthesis. The models implemented include:
- **Least Squares GAN (LS-GAN)**
- **Wasserstein GAN (WGAN)**
- **Wasserstein GAN with Gradient Penalty (WGAN-GP)**

## How Each GAN Works
### Least Squares GAN (LS-GAN)
LS-GAN modifies the loss function of traditional GANs to minimize the Pearson χ² divergence between real and generated distributions. Instead of using binary cross-entropy loss, LS-GAN employs a least-squares loss function, which helps to stabilize training and generate higher-quality images.

### Wasserstein GAN (WGAN)
WGAN introduces the Wasserstein distance (Earth Mover's Distance) to measure the divergence between real and generated distributions. It replaces the standard discriminator with a **critic** that learns to approximate the Wasserstein distance. WGAN improves training stability by removing the vanishing gradient problem and reducing mode collapse.

### Wasserstein GAN with Gradient Penalty (WGAN-GP)
WGAN-GP improves upon WGAN by introducing a gradient penalty term that enforces the Lipschitz constraint without requiring weight clipping. This penalty ensures stable training and better-quality image generation.

## Differences Between LS-GAN, WGAN, and WGAN-GP
- **LS-GAN:** Uses least-squares loss instead of binary cross-entropy, improving gradient flow and image quality.
- **WGAN:** Uses Wasserstein distance instead of JS divergence, allowing stable training and reducing mode collapse.
- **WGAN-GP:** Introduces gradient penalty instead of weight clipping to enforce Lipschitz continuity, leading to better convergence and higher-quality images.

## Evaluation Metrics
To assess the quality of generated images, the following metrics are used:
- **Inception Score (IS):** Measures the diversity and quality of generated images.
- **Fréchet Inception Distance (FID):** Computes the similarity between real and generated images.
- **Visual Inspection:** Generated images are analyzed to ensure they resemble real medical scans.

## Project Structure
- **GAN Models:** Different architectures for image generation.
- **Evaluation Methods:** Implementation of IS and FID scores for quantitative assessment.
- **TensorBoard Logging:** Visualization of training progress and image generation.

## Requirements
Ensure that you have the necessary libraries installed, including PyTorch, Torchvision, MedMNIST, and TensorBoard for logging and visualization.

## Running the Project
1. Train different GAN models.
2. Evaluate using IS and FID.
3. Inspect the generated images visually.

## Contributions
Contributions are welcome! Feel free to improve the evaluation process or add new GAN architectures.

## License
This project is open-source and available under the MIT License.
