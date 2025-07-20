
# 🧬 Prediction of Therapeutic Peptides using Deep Learning

This project leverages deep learning models—**LSTM**, **GRU**, and **RNN**—to accurately classify peptide sequences as therapeutic or non-therapeutic. We also implement a novel technique to identify **critical sequence motifs** that contribute to therapeutic potential, enhancing model interpretability and aiding drug discovery.

## 🧠 About the Project

Therapeutic peptides are short amino acid sequences with significant pharmaceutical value due to their high specificity and low toxicity. However, identifying such peptides is complex. Our deep learning framework automates this classification by analyzing the peptide sequences and identifying functional motifs.

This project:
- Trains and compares LSTM, GRU, and RNN models
- Analyzes over 4000 peptide sequences
- Achieves high accuracy (up to **92.24%** with LSTM)
- Identifies biologically significant **critical motifs** through perturbation analysis

## 📊 Dataset

- **Total Samples**: 4061 peptide sequences
- **Attributes**: `Sequence`, `Label` (0 or 1), `ID`
- **Label**: 
  - `1` - Therapeutic
  - `0` - Non-therapeutic
- **Sources**: Public peptide databases such as SATPdb and UniProt
- Preprocessing includes:
  - Cleaning invalid characters
  - Padding and tokenization
  - Label encoding

## 🏗️ Model Architectures

- **LSTM (Long Short-Term Memory)**  
  Bidirectional model that captures long-term dependencies. Best performance in classification accuracy.
- **GRU (Gated Recurrent Unit)**  
  Lighter alternative to LSTM with comparable performance and reduced computational cost.
- **Simple RNN**  
  Baseline architecture used for performance comparison.

All models use:
- Embedding Layer for sequence encoding
- Recurrent layers (LSTM/GRU/RNN)
- Dense output layer with sigmoid activation

## 🏋️‍♂️ Training & Evaluation

- **Stratified Train/Test Split** (with validation)
- **Loss Function**: Binary Cross-Entropy
- **Optimizer**: Adam
- **Early Stopping & Learning Rate Scheduling**
- **Evaluation Metrics**:
  - Accuracy
  - Precision
  - Recall
  - F1-Score
  - Confusion Matrix

| Model | Accuracy |
|-------|----------|
| LSTM  | 92.24%   |
| GRU   | 91.38%   |
| RNN   | 90.27%   |

## 🧩 Critical Motif Identification

We use a custom perturbation-based analysis to identify **key subsequences (motifs)** in peptides that influence the model's therapeutic predictions.

- Extracts k-mers from sequences
- Applies masking/replacement (alanine scanning)
- Measures drop in confidence to score motif relevance
- Visualizes motifs using heatmaps and sequence logos

The RNN model identified motifs in **80%** of sample peptides, demonstrating excellent interpretability.

## 📈 Results

- LSTM outperformed GRU and RNN in accuracy and stability.
- RNN showed best performance in identifying critical motifs.
- Balanced performance metrics across all models.
- All models demonstrated generalization on unseen peptide sequences.

## ⚙️ How to Run

1. Clone the repo  
   ```bash
   git clone https://github.com/yourusername/therapeutic-peptide-prediction.git
   cd therapeutic-peptide-prediction
   ```

2. Install dependencies  
   ```bash
   pip install -r requirements.txt
   ```

3. Run the Jupyter notebook  
   ```bash
   jupyter notebook Final_Code.ipynb
   ```

## 🧰 Technologies Used

- Python
- TensorFlow / Keras
- NumPy, Pandas
- Scikit-learn
- Matplotlib / Seaborn
- Jupyter Notebook
