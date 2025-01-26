# Top-DTI: Integrating Topological Deep Learning and Large Language Models for Drug Target Interaction Prediction

![Top-DTI Overview](images/pipeline.png)

---

## Top-DTI

We propose **Top-DTI** framework for predicting **Drug-Target Interaction (DTI)** by integrating  **Topological Data Analysis (TDA)** and **Large Language Models (LLMs)**. Top-DTI leverages **Persistent Homology (PH)** to extract topological features from protein contact maps and drug molecular images. Simultaneously, protein and drug LLMs generate semantically rich embeddings that capture sequential and contextual information from protein sequences and drug SMILES strings. TDA and LLM embeddings are combined through a learnable fusion mechanism that dynamically balances the contributions of topological and sequence-based features. The integrated representations are then fed into a heterogeneous **Graph Neural Network (GNN)** to learn relational information from the DTI network. Finally, the embeddings learned from the GNN are used to train a multilayer perceptron (MLP) classifier to predict DTIs.


## Top-DTI Workflow Steps

1. **Generate 2D Representations**  
   We created two-dimensional representations of drug molecular structures and protein contact maps to capture structural features.  
   - Drug images: Generated from SMILES using the RDKit library.  
   - Protein contact maps: Created using a transformer-based contact prediction model.  
   [Notebook: 01_generate_images.ipynb](Notebooks/01_generate_images.ipynb)

2. **Extract Topological Features**  
   We utilized **Persistent Homology (PH)** to extract topological features from drug molecular images and protein contact maps. 
   [Notebook: 02_topological_features.ipynb](Notebooks/02_topological_features.ipynb)

3. **Generate Sequence-Based Embeddings**  
   We employed pre-trained **LLLMs** to capture sequence-based features.  
   - **ProtT5**: For protein sequences.  
   - **MoLFormer**: For drug representations.  
   [Notebook: 03_LLM_embeddigns.ipynb](Notebooks/03_LLM_embeddigns.ipynb)
