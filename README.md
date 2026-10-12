# GANs and StyleGAN

## 📌 Overview

Generative Adversarial Networks (GANs) are deep learning architectures made up of two neural networks: a **Generator**, which produces artificial data, and a **Discriminator**, which determines whether the data is real or generated.

This project examines various GAN architectures and develops a simplified StyleGAN-inspired model using PyTorch and the Fashion-MNIST dataset.

## 🎯 Objectives

- Explore the working principles of different GAN architectures.
- Create artificial fashion images using generative models.
- Examine the StyleGAN architecture and its style-controlled image synthesis process.
- Implement latent-space interpolation and style-mixing techniques.

## 🧠 Types of GANs

- **Vanilla GAN:** A fundamental GAN model that uses fully connected layers in its generator and discriminator.
- **Conditional GAN (cGAN):** Produces synthetic data according to specified labels or input conditions.
- **DCGAN:** Employs convolutional neural networks (CNNs) to improve image generation.
- **SRGAN:** Reconstructs high-resolution images from low-resolution inputs.
- **CycleGAN:** Transforms images from one domain to another without requiring paired training data.
- **StyleGAN:** Enables image generation with controllable styles across different synthesis stages.
- **LAPGAN:** Creates images progressively through a multi-resolution image pyramid.

## 🎨 StyleGAN Architecture

StyleGAN converts a randomly generated latent vector into an intermediate latent representation. This representation provides style information that influences the image generation process.

**Main Components:**

- **Mapping Network:** Transforms the latent vector \(z\) into an intermediate style vector \(w\).
- **Learned Constant:** Supplies the initial feature representation for the synthesis network.
- **Synthesis Network:** Generates images through convolutional operations and upsampling.
- **AdaIN (Adaptive Instance Normalization):** Controls feature maps using style-dependent scaling and bias.
- **Discriminator:** Identifies whether an image is genuine or artificially generated.

### Architecture Flow

```text
Latent Input (z)
       |
       v
  Mapping Network
      z → w
       |
       v
  Learned Constant
       |
       v
  Synthesis Blocks
 (Upsampling + Conv
      + AdaIN)
       |
       v
  Generated Image
       |
       v
   Discriminator
   (Real or Fake)
```

## 🧪 Experiments

### 1. Image Generation

Train the generator and discriminator with the Fashion-MNIST dataset to produce synthetic grayscale images representing different types of clothing.

### 2. Latent-Space Interpolation

Generate intermediate latent vectors between two selected latent inputs to observe gradual visual transitions in the resulting images.

### 3. Style Mixing

Combine style representations from two different latent inputs at selected synthesis stages to demonstrate how different styles influence the generated images.

## ⚙️ Configuration

| Parameter | Value |
|---|---|
| Dataset | Fashion-MNIST |
| Number of Training Images | 5,000 |
| Image Resolution | 32 × 32 pixels |
| Latent Dimension | 32 |
| Batch Size | 128 |
| Number of Epochs | 10 |
| Optimizer | Adam |
| Framework | PyTorch |

## 🛠️ Technologies Used

- **Python:** Programming language used to implement the model.
- **PyTorch:** Framework for building and training neural networks.
- **Torchvision:** Library for accessing datasets and performing image transformations.
- **NumPy:** Supports numerical operations and array processing.
- **Matplotlib:** Used to display generated images, losses, and visualizations.
- **Jupyter Notebook:** Provides an interactive environment for executing experiments.

## 🚀 How to Run

Clone the project repository and enter the project directory:

```bash
git clone <your-repository-url>
cd GAN-StyleGAN
```

Install the necessary Python libraries:

```bash
pip install torch torchvision numpy matplotlib jupyter
```

Start Jupyter Notebook:

```bash
jupyter notebook
```

Open `STYLEGAN.ipynb` and execute each cell sequentially to run the model and experiments.

## 📊 Expected Results

- Synthetic grayscale images of fashion items.
- Graphical representations of generator and discriminator training losses.
- Latent-space interpolation images showing gradual changes between generated samples.
- Style-mixing visualizations demonstrating style-based image manipulation.

## ⚠️ Limitations

The developed model is a simplified implementation inspired by StyleGAN and does not reproduce the complete official StyleGAN architecture. The small training dataset, limited image resolution, and short training period may reduce the quality and diversity of the generated images.

## 🔮 Future Improvements

- Extend the training process by increasing the number of epochs.
- Experiment with larger datasets and higher-resolution images.
- Compare the model's performance with DCGAN and the official StyleGAN architecture.
- Assess generated image quality using appropriate evaluation metrics.

## ✅ Conclusion

This project explores the fundamental concepts of Generative Adversarial Networks and demonstrates style-based image synthesis using a simplified StyleGAN-inspired model. Image generation, latent-space interpolation, and style mixing provide practical insights into generative modeling with PyTorch and the Fashion-MNIST dataset.

## 👨‍💻 Author

Yashwanth M
