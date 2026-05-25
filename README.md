<div align="center">

# 🎵 Personalized Music Recommendation System  
## Using Graph Neural Network on LastFM Dataset

Graph-based collaborative filtering using **LightGCN** for personalized music recommendation.

</div>

---

## 📌 Overview

This project implements a **music recommendation system** using **Graph Neural Network (GNN)** on the **LastFM Dataset**.  
User listening history is transformed into a **bipartite graph User–Artist**, where:

- **User** → listener node
- **Artist** → music artist node
- **Edge** → listening interaction between user and artist

The main model used in this project is **LightGCN**, while **Popularity-Based Recommendation** is used as a baseline comparison.

---

## 🧠 Main Objectives

- Build User–Artist interaction graph from LastFM listening history
- Implement LightGCN for graph-based recommendation
- Compare LightGCN with popularity-based recommendation
- Evaluate recommendation quality using Top-K metrics
- Generate personalized artist recommendations

---

# 🏗️ System Pipeline

```text
LastFM Dataset
       ↓
Data Cleaning & Preprocessing
       ↓
User–Artist Interaction Construction
       ↓
User & Artist Encoding
       ↓
Train-Test Split
       ↓
Bipartite Graph Construction
       ↓
Normalized Adjacency Matrix
       ↓
LightGCN Training
       ↓
Top-K Recommendation
       ↓
Evaluation & Visualization
       ↓
Gradio Demo
```

---

# 📊 Dataset Information

### LastFM Dataset
Source:
https://www.kaggle.com/datasets/harshal19t/lastfm-dataset

### Dataset Statistics

| Information | Value |
|---|---|
| Total Rows | 166,153 |
| Unique Users | 11 |
| Unique Artists | 22,823 |
| Unique Tracks | 67,241 |
| User–Artist Interactions | 51,790 |

The dataset uses **implicit feedback**, where user preference is represented using:

```text
listen_count
```

which indicates how many times a user listened to a specific artist.

---

# 🤖 Model Architecture

The recommendation system uses **LightGCN (Light Graph Convolutional Network)**.

### Main Components

- Initial User & Artist Embedding
- Graph Propagation
- Embedding Aggregation
- BPR Loss Optimization
- Top-K Recommendation Ranking

### Why LightGCN?

LightGCN is chosen because:

- Specifically designed for recommendation systems
- Simpler than traditional GCN/NGCF
- Focuses on graph propagation
- Effective for collaborative filtering
- Lightweight architecture with strong recommendation performance

---

# 📈 Evaluation Metrics

The model is evaluated using:

| Metric | Purpose |
|---|---|
| Precision@10 | Measures recommendation relevance |
| Recall@10 | Measures retrieval coverage |
| NDCG@10 | Measures recommendation ranking quality |
| BPR Loss | Training optimization objective |

---

# 🏆 Best Experiment Result

| Configuration | Value |
|---|---|
| Best Model | LightGCN_dim64_layer3 |
| Embedding Dimension | 64 |
| Number of Layers | 3 |
| Learning Rate | 0.001 |
| Epochs | 30 |
| Batch Size | 1024 |

### Final Performance

| Metric | Score |
|---|---|
| Precision@10 | 0.827273 |
| Recall@10 | 0.039307 |
| NDCG@10 | 0.845210 |

The result shows that **LightGCN outperformed the popularity-based baseline** and produced more personalized recommendations.

---

# 📉 Hyperparameter Tuning

Several LightGCN configurations were tested by varying:

- Embedding dimension
- Number of propagation layers

### Tested Configurations

| Model | Embedding Dim | Layers |
|---|---|---|
| LightGCN_dim32_layer2 | 32 | 2 |
| LightGCN_dim64_layer2 | 64 | 2 |
| LightGCN_dim128_layer2 | 128 | 2 |
| LightGCN_dim64_layer1 | 64 | 1 |
| LightGCN_dim64_layer3 | 64 | 3 |

---

# 🔍 Key Findings

- Graph-based collaborative filtering performs better than popularity-based recommendation
- LightGCN successfully captures user–artist relational patterns
- Increasing propagation layers improves recommendation quality
- Lower training loss does not always produce better recommendation ranking
- NDCG@10 is the most representative metric for Top-K recommendation quality

---

# 🎨 Visualizations

The project includes several visualizations:

- User–Artist Bipartite Graph
- LightGCN Architecture Diagram
- Training Loss Curve
- Hyperparameter Comparison
- Recommendation Examples

---

# 🖥️ Demo

A simple interactive demo is implemented using **Gradio**.

### Demo Features

- Select existing user
- Generate Top-K artist recommendation
- Display personalized recommendation result

---

# ⚙️ Technologies & Libraries

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| PyTorch | LightGCN implementation |
| Pandas | Data preprocessing |
| NumPy | Numerical computation |
| Scikit-learn | Label encoding |
| NetworkX | Graph visualization |
| Matplotlib | Plotting & visualization |
| Gradio | Interactive demo |

---

# 👨‍💻 Team Members

| Name | Responsibility |
|---|---|
| Ahmad Fariz Khairi | Evaluation & Recommendation Analysis |
| Gerrardin Nabil Zulhian | Data Preprocessing & Graph Preparation |
| Muhammad Hilmy Mahardika | Core LightGCN Architecture |
| Muhammad Dzaky Maulana | Experiment Pipeline & Demo System |

---

# 📚 References

### Paper
He, X., Deng, K., Wang, X., Li, Y., Zhang, Y., & Wang, M. (2020).  
**LightGCN: Simplifying and Powering Graph Convolution Network for Recommendation**

### Dataset
LastFM Dataset — Kaggle

---

<div align="center">

### Graph Neural Network for Personalized Music Recommendation 🎵

</div>
