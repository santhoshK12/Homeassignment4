Neural Networks In-Home Assignment  4
University of Central Missouri  
Course: Neural Networks and Deep Learning  
Term: SUMMER 2025  
Student Name: SANTHOSH REDDY KISTIPATI  
Student ID: [700776947]  

EASYLY ACCUSS THE LINK : https://github.com/santhoshK12/Homeassignment4/tree/main

Overview of the Assignment  
This notebook provides solutions for six key tasks related to generative and adversarial learning, fairness in machine learning, and ethical AI implications. The practical parts are implemented in TensorFlow, covering basic GAN training, data poisoning attacks, and fairness audits.

Prerequisites  
Make sure the following are installed before running:

- Python 3.7 or above  
- TensorFlow 2.x  
- NumPy  
- Matplotlib  
- scikit-learn (for confusion matrix)

To install:
pip install tensorflow numpy matplotlib scikit-learn

Execution Instructions  
1. Open Google Colab (https://colab.research.google.com)  
2. Upload the notebook file "Homeassignment4.ipynb"  
3. Set the runtime type to GPU (optional but recommended)  
4. Click Runtime > Run all  
5. Results including plots, accuracy metrics, and confusion matrices will be displayed

---

# TASK 1: GAN Architecture (Q1)

This section introduces the architecture of Generative Adversarial Networks (GANs). The generator creates fake data to fool the discriminator, which tries to differentiate between real and generated data. Both models train in a minimax setup where the generator minimizes the discriminator's ability to classify correctly, and the discriminator maximizes classification accuracy.  
A sample architecture flowchart includes:  
- Input noise → Generator → Fake Image → Discriminator → Real/Fake classification  
The mathematical objectives:
- Generator: Minimize log(1 - D(G(z)))
- Discriminator: Maximize log(D(x)) + log(1 - D(G(z)))

---

# TASK 2: Ethical Issue in Generative AI (Q2)

This question focuses on misinformation. A malicious use-case is creating fake news images using GANs (e.g., fake protests). These can go viral, causing real-world damage.  
Two solutions are discussed:  
- **Watermarking**: Embeds a traceable signature in AI-generated content  
- **Content Moderation**: Using AI to detect and flag harmful/generated media  
These steps are essential to reduce risks and enforce accountability.

---

# TASK 3: Basic GAN Implementation (Q3)

This section implements a GAN to generate handwritten digits using the MNIST dataset.

- The **generator** converts 100-dimensional noise into 28×28 images.
- The **discriminator** classifies 28×28 images as real or fake.
- The model is trained for 100 epochs.
- Images are saved at Epochs 0, 50, and 100 to show progress.
- Generator and discriminator loss curves are plotted in `gan_losses.png`.

Files generated:
- `image_at_epoch_0001.png`
- `image_at_epoch_0051.png`
- `image_at_epoch_0100.png`
- `gan_losses.png`

---

# TASK 4: Data Poisoning Simulation (Q4)

This part simulates a data poisoning attack on an IMDB movie review sentiment classifier.

- First, the model is trained on clean data.
- Then, reviews mentioning “UC Berkeley” have their labels flipped (positive → negative and vice versa).
- The model is retrained on this poisoned data.
- A drop in accuracy and a change in confusion matrix indicate successful poisoning.

Output files:
- `cm_clean_model.png`: Confusion matrix for clean model  
- `cm_poisoned_model.png`: Confusion matrix for poisoned model  
- `accuracy_comparison.png`: Bar chart comparing both models

---

# TASK 5: Legal and Ethical Implications of Generative AI (Q5)

This section highlights concerns about generative models memorizing sensitive information (as seen with GPT-2) or producing copyrighted content (e.g., Harry Potter text).  
These issues violate:
- Privacy (unauthorized data memorization)
- Copyright law (generation of protected works)

Conclusion: Models should **not be trained** on such data unless proper licensing and privacy policies are enforced.

---

# TASK 6: Bias & Fairness – False Negative Rate Parity (Q6)

This section explains a fairness metric: **False Negative Rate Parity**.  
It measures whether different demographic groups (e.g., race or gender) experience **equal rates of false negatives**.

Why it matters:
- In applications like hiring or lending, high false negatives mean qualified individuals are unfairly rejected.
- A biased model will fail this metric, especially if trained on imbalanced or biased data.

Tool: **Aequitas** can audit such disparities and help organizations deploy fairer AI systems.
