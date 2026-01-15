# Federated Learning System for Sentiment Analysis

**Author:**  
**Mohammed Furqan Siddiq**

**Internship Organization:**  
GWING Software Technologies Pvt. Ltd.

---

## Overview

This project presents a **privacy-preserving Federated Learning system for Sentiment Analysis** built using the **Flower framework** and a **DistilBERT transformer model**.  
Unlike traditional centralized machine learning systems, this solution enables **distributed model training across multiple clients without sharing raw user data**.

The system demonstrates a **complete end-to-end pipeline**, including:
- Federated model training
- Secure parameter aggregation
- Model deployment via Flask REST API
- Interactive frontend for real-time sentiment prediction

---

## Problem Statement

Traditional sentiment analysis systems require centralized collection of user text data, leading to:
- Privacy risks
- Regulatory issues (GDPR, HIPAA)
- Security vulnerabilities
- Lack of user trust

**Goal:**  
To design a sentiment analysis system that:
- Learns from distributed datasets
- Preserves user privacy
- Maintains high prediction accuracy
- Is deployable in real-world environments

---

## Key Features

### 🔹 Privacy-Preserving Training
- Raw text data **never leaves client devices**
- Only model parameters are shared

### 🔹 Federated Learning with Flower
- Multiple simulated federated clients
- Secure aggregation using **FedAvg**

### 🔹 Transformer-Based NLP
- **DistilBERT** for high-accuracy sentiment classification
- Efficient fine-tuning across distributed clients

### 🔹 Real-Time Deployment
- Flask REST API with `/predict` endpoint
- JSON-based prediction responses

### 🔹 Interactive Frontend
- HTML + JavaScript interface
- Instant sentiment visualization
- Probability score display

### 🔹 Training Visualization
- Accuracy and loss curves
- Federated convergence analysis using Matplotlib

---

## System Architecture

The system follows a **decentralized federated architecture** consisting of:

1. **Federated Clients**
   - Local datasets
   - Local DistilBERT training
   - Parameter update generation

2. **Flower Federated Server**
   - Receives client updates
   - Aggregates weights using FedAvg
   - Produces global model

3. **Model Deployment Layer**
   - Flask REST API
   - Loads global model for inference

4. **Frontend Interface**
   - Sends prediction requests
   - Displays sentiment results

### 📐 Architecture Diagram

![System Architecture](assets/system_architecture.png)

---

## Federated Training Flow

1. Initialize global DistilBERT model
2. Distribute model to clients
3. Clients train locally on private data
4. Clients send updated parameters
5. Server aggregates updates (FedAvg)
6. Global model improves over rounds
7. Final model exported for deployment

![Federated Training Flow](assets/federated_flow.png)

---

## Algorithms Used

### Federated Averaging (FedAvg)


Where:
- `W_i` = client model weights  
- `n_i` = samples at client `i`  
- `N` = total samples  

Ensures fair aggregation across heterogeneous clients.

---

## Technologies Used

### Programming Languages
- Python 3.9+
- HTML, CSS, JavaScript

### Frameworks & Libraries
- Flower (Federated Learning)
- PyTorch
- Hugging Face Transformers
- Flask
- NumPy, Pandas
- Matplotlib

### Model
- DistilBERT-base-uncased

---

## Project Structure

~~~text
federated-sentiment-analysis/
├── clients/        # Federated client logic
├── server/         # Flower server & aggregation
├── model/          # DistilBERT training & export
├── api/            # Flask REST API
├── frontend/       # HTML/JS UI
├── metrics/        # Accuracy & loss logs
├── assets/         # Architecture & screenshots
└── README.md
~~~








