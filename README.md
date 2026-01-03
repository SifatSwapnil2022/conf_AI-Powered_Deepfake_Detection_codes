# 🧠 VFDNET: AI-Powered Deepfake Detection

This repository contains the official implementation of VFDNET (Vision Fake Detection Network), a transformer-based deep learning framework designed for robust detection of AI-generated and manipulated facial images.

---
# 📌 Background & Motivation

Although the term deepfake became popular in 2017, the manipulation of visual media dates back more than a century. Modern deepfakes, however, leverage GANs and transformer-based models, making them significantly harder to detect and posing serious threats to digital trust, privacy, and misinformation control.

VFDNET was developed to address this challenge by leveraging Vision Transformer (ViT) architecture for effective fake image detection.
---
# 🔍 What Is a Deepfake?

From our perspective:

A deepfake refers to a type of synthetic media where a person’s likeness in an image or video is replaced or manipulated using AI-driven techniques, often making the result indistinguishable from real content.
---
# 🚀 Overview of VFDNET

VFDNET is a pure transformer-based deepfake detection model that learns global image representations instead of relying solely on local convolutional features.

Key highlights:

Vision Transformer (ViT) backbone

Patch-based image representation

Global context modeling via self-attention

Binary classification: Real vs Fake
---
# 🏗️ Architecture & Workflow

1️⃣ Input Image

RGB image of size 224 × 224 × 3

Input images are resized and normalized before processing

2️⃣ Patch Embedding

Image is divided into 16 × 16 patches

Total patches: 196

Each patch is:

Flattened into a 768-dimensional vector

Projected into a learnable embedding space

3️⃣ Positional Embedding

Transformers are position-agnostic

Learnable positional encodings are added to patch embeddings to preserve spatial structure

Final input representation:

Patch Embedding + Positional Embedding

4️⃣ [CLS] Token

A special [CLS] token is prepended to the patch sequence

This token learns a global representation of the entire image

Input sequence format:

[CLS], Patch₁, Patch₂, ..., Patch₁₉₆

5️⃣ Transformer Encoder

The encoder consists of multiple stacked blocks, each containing:

Layer Normalization
Stabilizes training and accelerates convergence

Multi-Head Self-Attention (MHSA)
Enables each patch to attend to all others
Captures global dependencies and semantic inconsistencies

Feed-Forward Network (MLP)
Applies non-linear transformations to each patch independently

Residual Connections
Improve gradient flow and training stability

6️⃣ Feature Extraction

After encoder processing, the output corresponding to the [CLS] token is extracted

This vector represents the entire image

7️⃣ Classification Head

The [CLS] feature is passed through:

Fully connected MLP

Softmax layer

Final output: Real / Fake classification
---
# 🖼️ Model Architecture


<p align="center"> <img src="https://github.com/user-attachments/assets/47e70f35-8dec-4f83-904c-6bd437c63f27" alt="VFDNET Architecture" width="90%"> </p>

# 🌍 Impact

In an era increasingly dominated by AI-generated media, VFDNET contributes toward:

Combating misinformation

Enhancing media authenticity

Strengthening trust in digital content
---
# 📜 License

This project is released for research and academic use.
---
