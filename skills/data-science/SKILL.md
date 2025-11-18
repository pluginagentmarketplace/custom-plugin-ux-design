---
name: data-science
description: Master data science, machine learning, and AI development. Learn Python data stack, ML algorithms, deep learning with TensorFlow/PyTorch, and modern LLM applications.
---

# Data Science & Machine Learning

## Quick Start

### Python Data Analysis
```python
import pandas as pd
import numpy as np

# Load and explore data
df = pd.read_csv('data.csv')
print(df.head())
print(df.describe())

# Data visualization
import matplotlib.pyplot as plt
df['column'].plot(kind='histogram')
plt.show()
```

### Machine Learning with scikit-learn
```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier

# Load data
X, y = load_iris(return_X_y=True)

# Train-test split
X_train, X_test, y_train, y_test = train_test_split(X, y)

# Train model
clf = RandomForestClassifier()
clf.fit(X_train, y_train)

# Evaluate
score = clf.score(X_test, y_test)
```

### Deep Learning with PyTorch
```python
import torch
import torch.nn as nn

class SimpleNN(nn.Module):
    def __init__(self):
        super().__init__()
        self.linear1 = nn.Linear(10, 64)
        self.linear2 = nn.Linear(64, 10)

    def forward(self, x):
        x = torch.relu(self.linear1(x))
        return self.linear2(x)

model = SimpleNN()
```

## Python Data Stack

| Library | Purpose | Use Case |
|---------|---------|----------|
| NumPy | Numerical computing | Array operations, math |
| Pandas | Data manipulation | DataFrames, data cleaning |
| Scikit-learn | ML algorithms | Classification, regression |
| TensorFlow | Deep learning | Neural networks, production |
| PyTorch | Deep learning | Research, fast iteration |
| Matplotlib | Visualization | Static plots |
| Plotly | Interactive visualization | Interactive dashboards |
| Jupyter | Notebooks | Exploration & documentation |

## Key Topics

### Data Analysis & Preprocessing
- Data loading & exploration
- Missing value handling
- Outlier detection & treatment
- Feature engineering
- Data transformation
- Dimensionality reduction
- Data normalization & scaling

### Machine Learning Fundamentals
- Supervised vs unsupervised learning
- Classification algorithms
- Regression techniques
- Clustering methods
- Ensemble methods (Random Forest, Gradient Boosting)
- Cross-validation & evaluation metrics
- Hyperparameter tuning

### Deep Learning
- Neural network architecture
- Convolutional Neural Networks (CNN)
- Recurrent Neural Networks (RNN)
- Transformers & Attention mechanisms
- Transfer learning
- Fine-tuning pre-trained models
- Model optimization & quantization

### Natural Language Processing
- Text preprocessing & tokenization
- Word embeddings (Word2Vec, GloVe)
- Transformers (BERT, GPT)
- Sentiment analysis
- Named entity recognition
- Machine translation
- LLM fine-tuning & prompting

### Computer Vision
- Image classification
- Object detection (YOLO, Faster R-CNN)
- Semantic segmentation
- Instance segmentation
- Face recognition
- Image generation (GANs, Diffusion)

### LLM & AI Applications
- Prompt engineering
- Few-shot learning
- Retrieval-Augmented Generation (RAG)
- LangChain & LlamaIndex
- Vector databases (Pinecone, Weaviate)
- Fine-tuning LLMs
- Embeddings & semantic search

### MLOps & Production
- Model versioning (MLflow)
- Experiment tracking
- Model deployment
- API serving (FastAPI, Flask)
- Model monitoring & drift detection
- Retraining pipelines
- A/B testing ML models

## Best Practices

1. **Data Quality**
   - Exploratory data analysis (EDA)
   - Data validation
   - Missing value strategies
   - Outlier handling
   - Data documentation

2. **Model Development**
   - Start simple, iterate
   - Proper train-test split
   - Cross-validation usage
   - Regularization techniques
   - Avoid overfitting

3. **Evaluation**
   - Appropriate metrics selection
   - Baseline comparison
   - Error analysis
   - Business metric alignment
   - Reproducibility

4. **Production**
   - Model versioning
   - Containerization
   - Monitoring & alerting
   - Retraining strategy
   - A/B testing framework

## Advanced Resources

- NumPy: https://numpy.org
- Pandas: https://pandas.pydata.org
- Scikit-learn: https://scikit-learn.org
- PyTorch: https://pytorch.org
- TensorFlow: https://tensorflow.org
- Hugging Face: https://huggingface.co

## Related Skills

- python-data-science - Python libraries deep dive
- machine-learning - ML algorithms and theory
- deep-learning - TensorFlow, PyTorch, neural networks
- nlp-llm - NLP and large language models
- computer-vision - Image processing and analysis
- mlops-deployment - Model serving and monitoring
