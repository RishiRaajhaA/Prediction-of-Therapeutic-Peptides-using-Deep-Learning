
# 🧬 Prediction of Therapeutic Peptides using Deep Learning

This project leverages deep learning models—**LSTM**, **GRU**, and **RNN**—to classify peptide sequences as therapeutic or non-therapeutic. Additionally, it implements an advanced motif analysis system that helps identify critical subsequences affecting therapeutic predictions, improving biological interpretability and aiding peptide-based drug discovery.

## 🧠 About the Project

Therapeutic peptides play a pivotal role in modern medicine due to their high specificity and low toxicity. However, discovering such peptides is challenging and computationally intensive. This project:
- Uses LSTM, GRU, and RNN for peptide classification
- Achieves **up to 92.24%** classification accuracy
- Introduces a perturbation-based method to reveal **critical sequence motifs**
- Measures **inference time** for practical performance evaluation
- Implements **error handling** for robust motif analysis

## 📊 Dataset

- **Total Samples**: 4061 peptide sequences
- **Attributes**: `Sequence`, `Label` (0 or 1), `ID`
- **Label**: 
  - `1` - Therapeutic
  - `0` - Non-therapeutic
- **Source**: Public databases such as SATPdb and UniProt
- **Preprocessing**:
  - Sequence cleaning (special characters, casing)
  - Tokenization and padding
  - Label encoding

## 🏗️ Model Architectures

- **LSTM** - Best accuracy, strong for long-range dependencies
- **GRU** - Faster, lighter, and nearly as effective
- **RNN** - Baseline model with strong motif identification performance

All models include:
- Embedding layer
- Bidirectional recurrent layers (LSTM/GRU/RNN)
- Dense output with sigmoid activation

## 🏋️‍♂️ Training & Evaluation

- **Stratified train/validation/test split**
- **Loss Function**: Binary Cross-Entropy
- **Optimizer**: Adam
- **Regularization**: Dropout
- **Callbacks**: EarlyStopping, ReduceLROnPlateau

### 📈 Accuracy Scores

| Model | Accuracy |
|-------|----------|
| LSTM  | 92.24%   |
| GRU   | 91.38%   |
| RNN   | 90.27%   |

### 🕒 Inference Time

Inference time is measured for each model to evaluate their real-time applicability.

## 🧩 Critical Motif Identification

- **Perturbation analysis** is applied to mask k-mers and analyze their impact.
- Models return confidence scores before and after modification.
- Top motifs are ranked based on confidence drop.
- Results include robust **error handling** for invalid or short sequences.

### 📊 Summary Output
- Critical motif detection is performed for all therapeutic peptides.
- **Motif Coverage**:
  - RNN: ~80%
  - LSTM: ~20%
  - GRU: ~10%

## 📈 Results

- **LSTM** excels in predictive accuracy.
- **RNN** is strongest for identifying interpretable motifs.
- Balanced precision, recall, and F1-score across models.
- Enhanced visualizations and reporting for model performance and motif findings.

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

3. Launch the notebook  
   ```bash
   jupyter notebook Final_Code.ipynb
   ```

## 🧰 Technologies Used

- Python
- TensorFlow / Keras
- NumPy, Pandas
- Scikit-learn
- Matplotlib, Seaborn
- Jupyter Notebook
