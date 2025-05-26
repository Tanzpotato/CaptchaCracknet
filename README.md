# CaptchaCrackNet

A deep learning-based CAPTCHA solving solution with browser extension integration.

## Project Structure

- **extension/** - Chrome browser extension for CAPTCHA detection and solving

  - `content.js` - Content script that runs on web pages
  - `popup.html` - Extension popup interface
  - `popup.js` - JavaScript for the popup functionality
  - `manifest.json` - Extension configuration
  - `icon.png` - Extension icon

- **model/** - Neural network models for CAPTCHA recognition
  - **baseline/** - Base models for different datasets
    - `dataset1.ipynb` - Model for the first dataset
    - `dataset2.ipynb` - Model for the second dataset
    - `dataset2_resnet.ipynb` - ResNet-based model for the second dataset
    - `dataset3.ipynb` - Model for the third dataset
    - `dataset4.ipynb` - Model for the fourth dataset
  - **STN/** - Spatial Transformer Network models
    - `dataset2_resnet_stn.ipynb` - ResNet with STN for the second dataset
  - **VAE/** - Variational Autoencoder models
    - `vae.ipynb` - VAE implementation for CAPTCHA denoising

## Overview

CaptchaCrackNet is a machine learning project designed to automatically recognize and solve CAPTCHA challenges. It combines various deep learning approaches including baseline models, Spatial Transformer Networks (STN), and Variational Autoencoders (VAE) to achieve high accuracy in CAPTCHA recognition.

This project was built as a part of IEEE Envision 2025.

## Browser Extension

The included Chrome extension built using HTML, JS, and Manifest V3 allows for real-time CAPTCHA detection and solving on web pages. The extension interacts with the trained models to provide automated CAPTCHA solutions. When the user clicks on the image, it is sent to the model API (Hugging Face), which returns the CAPTCHA text to the extension and gets auto-filled into the text input field. 

Here is a quick demo of it.

https://github.com/user-attachments/assets/da045090-c4c3-4dda-ac9b-8bc1b65e7318



## Models

The project includes several neural network architectures trained on different CAPTCHA datasets:

- **Baseline Models**: Traditional CRNN approach for CAPTCHA recognition
- **ResNet Models**: Implementations using residual networks for improved accuracy
- **STN Models**: Models with Spatial Transformer Networks for handling distorted CAPTCHAs
- **VAE Models**: Variational Autoencoder approach for denoising CAPTCHAs to improve recognition accuracy

## Performance on Various CAPTCHA Types

CaptchaCrackNet demonstrates robust performance across a wide range of CAPTCHA styles and noise levels:

- **Text-based CAPTCHAs**: Achieves 95%+ accuracy on standard alphanumeric CAPTCHAs with varying fonts, rotations, and character spacing
- **Noise Resistance**: Successfully processes CAPTCHAs with:
  - Background noise and patterns
  - Random line interference
  - Dot/speckle noise
  - Blur and distortion effects
  - Varying contrast levels
- **Advanced CAPTCHA Handling**:
  - The STN models excel at recognizing highly warped or distorted text
  - VAE preprocessing significantly improves recognition of noisy CAPTCHAs by effectively filtering out interference. In this project specifically , We chose to use standard autoencoders due to the low complexity of noise and interference in our datasets.
  - ResNet architectures provide superior accuracy on complex multi-character sequences

Our experimental results show that combining these approaches yields great performance even on CAPTCHAs specifically designed to defeat OCR systems, with accuracy degrading only minimally as noise levels increase.

## Contributors:

### Mentors:

Was mentored by Dinesh Manideep and Akhil Sakthieswaran , Seniors from NITK


