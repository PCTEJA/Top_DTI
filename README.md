# Top-DTI: Integrating Topological Deep Learning and Large Language Models for Drug Target Interaction Prediction

![Top-DTI Overview](images/pipeline.png)

---

## Top-DTI

We propose **Top-DTI**, a framework for **Drug-Target Interaction (DTI)** prediction that integrates embeddings learned from **Topological Data Analysis (TDA)** and **Large Language Models (LLMs)**. The embeddings are extracted from drug and protein LLMs to capture sequential and contextual information from protein sequences and drug SMILES strings. Topological features are derived using **Persistent Homology (PH)** applied to drug molecular images and protein contact maps.

These embeddings are combined through a learnable fusion mechanism that dynamically balances the contributions of topological and sequence-based features. The integrated representations are then fed into a heterogeneous **Graph Neural Network (GNN)** to learn relational information from the DTI network. Finally, the embeddings learned from the GNN are used to train a multilayer perceptron (MLP) classifier to predict Drug-Target Interactions (DTIs).


