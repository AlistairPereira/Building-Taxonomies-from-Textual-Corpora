## Note on Notebook Rendering
If GitHub shows an **"Unable to render code block"** message, please download the notebook file and open it locally in Jupyter Notebook or JupyterLab.
The file contains heavy computations (embeddings and clustering), which may exceed GitHub’s rendering limits.

**Language Model–Driven Hierarchical Taxonomy Construction**

**Master’s Thesis Project – Applied Data Science**
This project builds a multi-level product taxonomy automatically using sentence embeddings, clustering algorithms, and a Large Language Model (LLaMA) for category naming.
The system constructs a hierarchy (C → B → A) directly from product descriptions — without manually defining category rules.

**🚀 Problem**
Large product catalogs require structured taxonomies.
Manual category design does not scale and becomes inconsistent over time.
This project proposes a fully data-driven pipeline to automatically generate a hierarchical taxonomy from raw product text.

**🏗️ Methodology**
The framework follows a bottom-up approach:


**1️ Text Preprocessing**
Cleaning and normalization of product metadata

**2️ Sentence Embeddings (SBERT)**
Models compared:
all-MiniLM-L6-v2
multi-qa-mpnet-base-dot-v1
all-mpnet-base-v2 ✅ (Selected)
Embeddings capture semantic similarity between products.

**3️ Dimensionality Reduction**
UMAP for structuring embedding space

**4 C-Level Clustering**
OPTICS (density-based clustering)

**5️ B-Level Clustering**
Agglomerative clustering on C-level centroids

**6 A-Level Category Naming**
LLaMA-based Large Language Model
Generates interpretable category names
Uses clustered product evidence for structured naming

**7️ Evaluation**
Structural: Purity, NMI
Semantic: Cosine Similarity, BERTScore
Train–Test split to simulate real-world deployment

**🧠 Key Contributions**
Fully unsupervised hierarchical taxonomy construction,
Multi-level clustering (C → B → A),
LLaMA-driven automatic category naming,
Combined structural + semantic evaluation,
Realistic train–test simulation

**🛠️ Tech Stack**
Python,
SentenceTransformers,
UMAP,
OPTICS,
Agglomerative Clustering,
LLaMA (LLM-based naming),
Scikit-learn,
BERTScore.
