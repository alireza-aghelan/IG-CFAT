# IG-CFAT
[[Paper Link]](https://arxiv.org/abs/2406.13815)

Welcome to the official GitHub repository for IG-CFAT, an improved GAN-Based model for effectively exploiting transformers in real-world image super-resolution tasks. 

# Overview

In the field of single image super-resolution (SISR), transformer-based models have showcased remarkable progress. However, their application and efficiency in real-world image super-resolution are less noticed, presenting substantial opportunities for improvement. IG-CFAT bridges this gap by leveraging the strengths of some recent techniques to enhance real-world image super-resolution, surpassing existing state-of-the-art (SOTA) models.

## Key Features

- **Composite Fusion Attention Transformer (CFAT)**: Our model builds on the CFAT architecture, which has already demonstrated superior performance in classic image super-resolution tasks.
- **Semantic-Aware Discriminator (SeD)**: To reconstruct image details more accurately and significantly improve perceptual quality, IG-CFAT incorporates a semantic-aware discriminator.
- **Adaptive Degradation Model**: We utilize an adaptive degradation model to better simulate real-world image degradations, making our approach more robust and effective.
- **Wavelet Losses**: By adding wavelet losses to the conventional loss functions used in GAN-based super-resolution models, IG-CFAT can reconstruct high-frequency details more efficiently.

# Results

Our experiments demonstrate that IG-CFAT sets new benchmarks in real-world image super-resolution, outperforming SOTA models in both quantitative and qualitative metrics. The results are shown in the following Figures.
<br><br>
<img src="./figures/1.jpg" width="600">

Quantitative comparison between IG-CFAT and GAN-based SR methods.
<br><br>
<img src="./figures/2.jpg" style="margin: 0; padding: 0;">
<img src="./figures/3.jpg" style="margin: 0; padding: 0;">

Visual comparison of IG-CFAT with GAN-based SR methods.
<br><br>

# Installation

Clone the repository and navigate into the directory:

```bash
git clone https://github.com/alireza-aghelan/IG-CFAT
cd IG-CFAT
```
Install the basic dependencies and requirements:

```bash
pip install basicsr
pip install pywavelets
pip install -r requirements.txt
python setup.py develop
conda create -n SeD python=3.9
conda activate SeD
pip install torch==1.9.0+cu111 torchvision==0.10.0+cu111 torchaudio==0.9.0 -f https://download.pytorch.org/whl/torch_stable.html
pip install git+https://github.com/openai/CLIP.git
```

# Training

- Modify the configuration files in ./options/train according to your requirements.
- Run the following command to train the MSE model from scratch using L1 loss and adaptive degradation model:

```bash
python igcfat/train.py -opt IG-CFAT/options/train/train_IG_CFAT_SRx4_mse_model.yml --auto_resume
```

- Place the pre-trained MSE model in the ./experiments/pretrained_models directory.
- Run the following command to fine-tune the MSE model using our GAN framework:

```bash
python igcfat/train.py -opt IG-CFAT/options/train/train_IG_CFAT_SRx4_finetune_from_mse_model.yml --auto_resume
```

# Testing

- Place testing data in the ./LR directory.
- Place pre-trained models in the ./experiments/pretrained_models directory.
- Modify the specific settings in ./options/test/IG_CFAT_SRx4.yml according to your requirements.
- Run the following command to test the model:

```bash
python IG-CFAT/igcfat/test.py -opt IG-CFAT/options/test/IG_CFAT_SRx4.yml
```

The results will be saved in the ./results folder.

Our code is built on [BasicSR](https://github.com/XPixelGroup/BasicSR), [CFAT](https://github.com/rayabhisek123/CFAT), and [HAT](https://github.com/XPixelGroup/HAT). Thanks to their great work.

# Contact

If you have any questions, please email alireza.aghelan20@gmail.com.
