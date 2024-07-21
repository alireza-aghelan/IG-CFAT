# IG-CFAT
[[Paper Link]](https://arxiv.org/abs/2406.13815)

Welcome to the official GitHub repository for IG-CFAT, an improved GAN-Based model for effectively exploiting transformers in real-world image super-resolution tasks. 

# Overview

In the field of single image super-resolution (SISR), transformer-based models have showcased remarkable progress. However, their application and efficiency in real-world image super-resolution are less noticed, presenting substantial opportunities for improvement. IG-CFAT bridges this gap by leveraging the strengths of some recent techniques to enhance real-world image super-resolution, surpassing existing state-of-the-art (SOTA) models.

# Key Features


- **Composite Fusion Attention Transformer (CFAT)**: Our model builds on the CFAT architecture, which has already demonstrated superior performance in classic image super-resolution tasks. [CFAT](https://github.com/rayabhisek123/CFAT)
- **Semantic-Aware Discriminator**: To reconstruct image details more accurately and significantly improve perceptual quality, IG-CFAT incorporates a semantic-aware discriminator. [SeD](https://github.com/lbc12345/SeD)
- **Adaptive Degradation Model**: We utilize an adaptive degradation model to better simulate real-world image degradations, making our approach more robust and effective. [DASR](https://github.com/csjliang/DASR) - [StarSRGAN](https://github.com/kynthesis/StarSRGAN)
- **Wavelet Losses**: By adding wavelet losses to the conventional loss functions used in GAN-based super-resolution models, IG-CFAT can reconstruct high-frequency details more efficiently. [Wavelettention](https://github.com/mandalinadagi/Wavelettention)

# Results

Our experiments demonstrate that IG-CFAT sets new benchmarks in real-world image super-resolution, outperforming SOTA models in both quantitative and qualitative metrics. The results are shown in the following Figures.
<br><br>
<img src="https://github.com/user-attachments/assets/239d990d-d56f-424f-8e8e-52702669a1ae" width="600">

Quantitative comparison between IG-CFAT and GAN-based SR methods.
<br><br>
<img src="https://github.com/user-attachments/assets/33f57ac6-5a3a-4234-a63d-58124dd5e562" style="margin: 0; padding: 0;">
<img src="https://github.com/user-attachments/assets/924e7a9f-d5e7-4d8c-8a07-8126c0799032" style="margin: 0; padding: 0;">

Visual comparison of IG-CFAT with GAN-based SR methods.
<br><br>
Our code is built on [BasicSR](https://github.com/XPixelGroup/BasicSR), [CFAT](https://github.com/rayabhisek123/CFAT), and [HAT](https://github.com/XPixelGroup/HAT). Thanks to their great work.
