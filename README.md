# MC Dropout: Reproducing Gal & Ghahramani (2016)

This repository contains an implementation of the key experiments from the paper:

> Gal, Y., & Ghahramani, Z. (2016). *Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning*. ICML.

Reproduced and analyzed the results on **uncertainty estimation** using **Monte Carlo Dropout (MC Dropout)**, covering both regression and classification tasks.

---

## 🎯 Introduction & Theoretical Background

The goal of this project is to investigate how **dropout**, originally introduced as a regularization method, can be interpreted as **approximate Bayesian inference** when applied at both training and test time. This perspective enables us to model **uncertainty** in neural networks without significantly increasing computational cost.

By implementing **Monte Carlo Dropout**, we simulate posterior sampling by performing multiple stochastic forward passes at inference time. This allows us to:
- Quantify uncertainty in regression outputs.
- Detect model confidence degradation on out-of-distribution (OOD) classification inputs.
- Compare different activation functions and dropout configurations.

---

## 📈 Results Overview

### ✅ Regression: Mauna Loa CO₂ dataset
- **Standard dropout** fails to express any uncertainty.
- **MC Dropout (ReLU)** captures predictive variance that increases beyond the training range.
- **MC Dropout (Tanh)** yields smoother and better-calibrated uncertainty bands.
- Even **T=10 samples** are sufficient to capture meaningful variance.

### ✅ Classification: Rotated MNIST digits
- Uncertainty increases with rotation, as inputs move away from the training distribution.
- MC Dropout shows **increased entropy** and **less overconfidence** compared to standard dropout.
- Standard dropout misclassifies confidently, highlighting its risk in real-world settings.

---

## 🧠 Key Concepts

- **Dropout as Variational Inference**
- **Bayesian Deep Learning**
- **Epistemic vs. Aleatoric Uncertainty**
- **Predictive Mean and Variance via Sampling**
- **Out-of-distribution Robustness**

---

## 📘 References

- Gal, Y., & Ghahramani, Z. (2016). *Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning*. Proceedings of ICML.
- Paszke, A. et al. (2019). *PyTorch: An Imperative Style, High-Performance Deep Learning Library*. NeurIPS.
- LeCun, Y. et al. *The MNIST Database of Handwritten Digits*.  
- Harris, C.R. et al. (2020). *Array programming with NumPy*. Nature.
- Hunter, J.D. (2007). *Matplotlib: A 2D Graphics Environment*. CiSE.
- McKinney, W. (2010). *Data Structures for Statistical Computing in Python*. SciPy Conf.

---

## 👩‍💻 Author

**Zabdy Leos**  
MSc. Digital Security — EURECOM  
LinkedIn: [www.linkedin.com/in/zabdy-leos]  

---
