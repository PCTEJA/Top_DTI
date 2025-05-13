## Top-DTI: Integrating Topological Deep Learning and Large Language Models for Drug Target Interaction Prediction

![Top-DTI Overview](images/pipeline.png)

---

## Top-DTI


We propose **Top-DTI** framework for predicting Drug-Target Interaction (DTI) by integrating  Topological Data Analysis (TDA) and Large Language Models (LLMs). Top-DTI leverages Persistent Homology (PH) to extract topological features from protein contact maps and drug molecular images. Simultaneously, protein and drug LLMs generate semantically rich embeddings that capture sequential and contextual information from protein sequences and drug SMILES strings. TDA and LLM embeddings are combined through a learnable fusion mechanism that dynamically balances the contributions of topological and sequence-based features. The integrated representations are then fed into a heterogeneous Graph Neural Network (GNN) to learn relational information from the DTI network. Finally, the embeddings learned from the GNN are used to train a multilayer perceptron (MLP) classifier to predict DTIs.


## How to Run Top-DTI

1. **Generate 2D Representations**  
   Generate two-dimensional representations of drug molecular structures and protein contact maps to capture structural features:  
   - Drug Images: Generated from SMILES using the RDKit library.  
   - Protein Contact Maps: Created using a transformer-based contact prediction model. 

    [Run Notebook: 01_generate_images.ipynb](Notebooks/01_generate_images.ipynb)

2. **Extract Topological Features**  
   Extract topological features from drug molecular images and protein contact maps using Persistent Homology.

    [Run Notebook: 02_topological_features.ipynb](Notebooks/02_topological_features.ipynb)

3. **Generate Sequence-Based Embeddings**  
   Capture sequence-based features using LLMs:  
   - [ProtT5](https://github.com/agemagician/ProtTrans): For protein sequences.  
   - [MoLFormer](https://github.com/IBM/molformer): For drug representations. 

    [Run Notebook: 03_LLM_embeddigns.ipynb](Notebooks/03_LLM_embeddigns.ipynb)

4. **Top-DTI Evaluation and Results**
   
    The embeddings generated from [Step 2: Topological Features](Notebooks/02_topological_features.ipynb) and [Step 3: Sequence-Based Embeddings](Notebooks/03_LLM_embeddigns.ipynb) are utilized to evaluate the performance of Top-DTI on benchmark datasets:

    - [BioSNAP Dataset Evaluation: biosnap_random.ipynb](Notebooks/biosnap_random.ipynb)  
    - [BioSNAP Unseen Drug Dataset Evaluation: biosnap_unseen_drug.ipynb](Notebooks/biosnap_unseen_drug.ipynb) 
    - [BioSNAP Unseen Target Dataset Evaluation: biosnap_unseen_target.ipynb](Notebooks/biosnap_unseen_target.ipynb)   
    - [Human Dataset Evaluation: human_random.ipynb](Notebooks/human_random.ipynb)  
    - [Human Cold Dataset Evaluation: human_cold.ipynb](Notebooks/human_cold.ipynb)  


## Datasets

The public benchmark datasets are available in the [datasets](datasets) folder for direct access.  

- BioSNAP and Human datasets were obtained from [DrugLAMP](https://github.com/Lzcstan/DrugLAMP) repository.  
- BioSNAP Unseen Drug and BioSNAP Unseen Target datasets were sourced from [ConPLex_dev](https://github.com/samsledje/ConPLex_dev) repository.

## Installation Guide

The environment.yml file and requirements.txt are provided in the main repository for your convenience.

The provided `environment.yml` file can be used to create the required Conda environment as follows:
```bash
conda env create -f environment.yml
conda activate prot_fun

