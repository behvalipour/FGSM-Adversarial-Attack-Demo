
# FGSM-Adversarial-Attack-Demo: Assessing Model Robustness

## 🛡️ Technical AI Safety Focus: Adversarial Robustness

This project serves as a hands-on demonstration of **Adversarial Robustness**, a critical challenge in creating safe and reliable AI systems. It proves that a trained neural network can be easily fooled by tiny, human-imperceptible perturbations added to the input data.

**Problem Addressed:** The experiment confirms that the model's decision boundary is highly non-linear and brittle. A model that performs well on clean data (high accuracy) can be trivially misled, highlighting a critical vulnerability for safety-critical applications like autonomous vehicles or medical imaging.

---

## ⚙️ Technical Implementation

* **Method:** Fast Gradient Sign Method (FGSM) - A **white-box attack** that calculates the gradient of the loss with respect to the input image, then pushes the image pixels in the direction that maximizes the classification error.
* **Formula Implemented:** $x_{adv} = x + \epsilon \cdot \text{sign}(\nabla_x J(\theta, x, y))$
* **Tools:** PyTorch, Torchvision, NumPy, Matplotlib
* **Dataset:** MNIST (Handwritten Digits)
* **Code:** The entire implementation is available in `FGSM_Adversarial_Attack_Demo.ipynb`.

---

## 📊 Key Results and Findings

### 1. Model Accuracy Collapses under Attack

This plot shows the model's accuracy as the perturbation strength ($\epsilon$) increases. The rapid drop demonstrates the inherent vulnerability of the CNN.


**Finding:** The model's accuracy plummeted from **97.8% ($\epsilon=0.0$) to 20.8% ($\epsilon=0.3$)**, indicating a severe lack of adversarial robustness. This small change in $\epsilon$ is visually indiscernible to a human.

### 2. Visualization of Misclassification

The grid below visualizes the attack success. Each cell shows the model's prediction for an image: `[Original Label] -> [Adversarial Prediction]`.


**Finding:** Notice that even at low perturbation levels (e.g., $\epsilon=0.1$), the model consistently misclassifies the digits (e.g., a '6' classified as a '4', a '4' classified as a '1'), despite the images remaining clear to the human eye. This visually confirms the successful exploitation of the model's vulnerability.

---

## 🚀 How to Run the Code

1.  Clone this repository: `git clone [Your Repo URL]`
2.  Open the `FGSM_Adversarial_Attack_Demo.ipynb` file in Google Colab or Jupyter Notebook.
3.  Run the cells sequentially to reproduce the model training, attack implementation, and all plotted results.
