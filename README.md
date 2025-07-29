# GAN-Based Sketch Generation with QuickDraw: From Toy Data to Horses

This repository chronicles my journey and experiment with **Generative Adversarial Networks (GANs)** for creating hand-drawn sketches based on the **Google QuickDraw dataset**. The project starts with basic GANs on synthetic 2D data, moves on to DCGANs on simple smiley faces, and culminates in more complex sketches—horses—along with technical and artistic takeaways.

--- 

## Project Overview

- **Stage 1:** GAN training and visualization in the intutitive mode on synthetic toy 2D data
- **Stage 2:** DCGAN for simple sketch generation (Smiley Faces)
- **Stage 3:** Extension of DCGAN to intricate sketch generation (Horses)

---

## Objectives

- Develop a hands-on experience with adversarial learning on simple data.
- Extend to real-world creative sketch generation from toy problems.
- Compare and evaluate the performance of GAN as the sketch complexity varies.

---

## Technologies & Tools

- Python 3.8+
- PyTorch (or TensorFlow)
-  Google Colab
- NumPy, Matplotlib, Pandas

---

## Dataset

- **Source:** [Google QuickDraw Dataset](https://github.com/googlecreativelab/quickdraw-dataset)
- **Classes Used:**
  - Smiley Face (simple, low variation)
  - Horse (complex, high variation)

---

## Implementation Details

### Stage 1: Toy 2D GANs

- **Architecture:** MLP-based Generator & Discriminator (2-3 layers)
- **Data:** 2D shapes (moons, rings, circles)
- **Objective:** Visualize GAN learning, mode collapse, and generator evolution

### Stage 2: Smiley Face DCGAN

- **Generator:** Transposed convolutions, batch normalization, ReLU/Tanh
- **Discriminator:** Convolutions, LeakyReLU, batch normalization
- **Input/Output:** 100-dim noise → 28x28 pixel image
- **Training:** Adam optimizer, binary cross-entropy, label smoothing

### Stage 3: Horse DCGAN

- **Tweaks to Architecture:** Increased feature maps, deeper generator, ELU activations
- **Strategy:** Hyperparameter tuning (learning rate, batch size) for stability
- **Objective:** Generate diverse, recognizable horses

---

## Training Configurations

- **Epochs:** 5–20 (stage-dependent)
- **Batch Size:** 128
- **Optimizer:** Adam (`lr=2e-4`, β1=0.5, β2=0.999)
- **Loss:** Binary Cross-Entropy
- **Label Smoothing:** On

---

## Results: Qualitative Summary

| Stage        | Sketch Type   | Stability         | Visual Quality    | Loss Curves       |
|--------------|--------------|-------------------|-------------------|-------------------|
| Toy 2D GAN   | Moons/Rings  | ✅ Intuitive      | ✅ Clear          | ✅ Smooth         |
| DCGAN Smiley | Smiley Face  | ✅ Stable         | ✅ Good/Varied    | ✅ Converged      |
| DCGAN Horse  | Horse        | ⚠️ Challenging   | ⚠️ Mixed/Abstract | ⚠️ Unstable       |

---

## Key Insights

- GANs learn low-dimensional, simple patterns quickly and naturally.
- DCGANs perform well at simple sketches but poorly when visual complexity increases.
- Varied, abstract sketches (e.g., horses) expose mode collapse and shortcomings in baseline DCGANs.

---

## Visualizations & Additional Details

- Generator and discriminator loss plots per stage
- Real vs. generated samples (side-by-side)
- For complete writeup, methodology, and additional visuals, refer to **GAN_REPORT.docx** (attached).

---

## How to Use / Reproduce

1. Download the corresponding QuickDraw classes (`smiley face` and `horse`).
2. Synchronize with the given Google Colab notebooks for each phase.
3. Keep the same data splits, random seeds, and hyperparameters for reproducibility.
4. Observe loss curves and sample outputs to detect training issues.

---

## Future Work

- Try **Progressive GANs** for detailed drawings
- Incorporate attention or multi-phase architectures for more detail
- Quantitative measures (e.g., FID, Inception Score) for assessment
- Data augmentation for increased diversity

---

## References

1. Radford, A., Metz, L., & Chintala, S. (2016). ["Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks"](https://arxiv.org/abs/1511.06434)
2. Goodfellow, I., et al. (2014). "Generative Adversarial Nets"
3. [Google QuickDraw Dataset](https://github.com/googlecreativelab/quickdraw-dataset)

---

## Author
**UMAR**


---
