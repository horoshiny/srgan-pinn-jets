# Super-Resolution of Calorimeter Jet Images using GAN and PINN

## Problem Statement

This project focuses on reconstructing high-resolution (125×125) calorimeter jet images from low-resolution inputs.
The dataset consists of three-channel images representing energy deposits for two classes of particles: quarks and gluons.

---

## Approach

### Baseline Model

A standard super-resolution model trained using pixel-wise Mean Squared Error (MSE) loss.
This serves as a reference for evaluating improvements.

###GAN + PINN Model

An advanced model that integrates:

* **Generative Adversarial Network (GAN)** for perceptual quality enhancement
* **Physics-Informed Neural Network (PINN)** constraints to enforce physical consistency

This hybrid approach aims to balance:

* Visual realism (GAN)
* Physical correctness (PINN)

---

## Model Design

* **Generator:** CNN with residual connections for image reconstruction
* **Discriminator:** CNN-based classifier to distinguish real vs generated images
* **Loss Function:**

  * Pixel Loss (MSE)
  * Adversarial Loss (GAN)
  * Physics-informed Loss (PINN constraints)

---

##Results

### Baseline Output

![Baseline](results/baseline.png)

### GAN + PINN Output

![PINN](results/pinn.png)

### Observations

* The model successfully reconstructs the central jet structure from low-resolution input
* GAN improves structural reconstruction compared to baseline
* PINN constraints help maintain physically meaningful patterns
* Outputs appear slightly smoother, indicating a trade-off between realism and physical consistency

---

##Limitations

* Slight blurring due to dominance of reconstruction and physics-informed losses
* GAN not fully utilized for high-frequency detail generation
* Error patterns suggest scope for improved loss balancing

---

##Future Work

* Incorporate perceptual loss (e.g., VGG-based) for sharper outputs
* Improve adversarial training stability
* Apply **Uncertainty Quantification (UQ)** to estimate confidence in reconstructed jet images
* Extend PINN framework to probabilistic modeling for high-energy physics applications

---

## ▶️ How to Run

1. Install dependencies:

```
pip install -r requirements.txt
```

2. Run notebooks:

* `notebooks/baseline_sr.ipynb`
* `notebooks/pinn_gan.ipynb`

---

## 📌 Repository Structure

```
srgan-pinn-jets/
│
├── notebooks/
├── results/
├── README.md
└── requirements.txt
```
