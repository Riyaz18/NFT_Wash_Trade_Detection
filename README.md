# NFT_Wash_Trade_Detection
Detecting potential NFT wash trades using ensemble machine learning with synthetic data.
# 🧠 NFT Wash Trade Detection using Ensemble Machine Learning

This project focused on detecting **wash trading in NFT markets** using synthetic data and ensemble machine learning technique. It include feature engineering, handling data imbalance, model training, and saving the final model for deployment or further analysis

---

## 🚀 Project Overview

Wash trading is a market manipulation tactic where the same entity acts as both buyer and seller to inflate asset value or volumes. This project simulates such behaviors using synthetic data and builds a predictive model to detect these pattern.

**Key Highlights:**
- Synthetic dataset simulating NFT transaction
- Extensive feature engineering based on address pattern, time bins, and price volatility
- Ensemble modeling using Soft Voting
- Evaluation with classification metrics, ROC-AUC,& PR-AUC
- Finally model and scaler saved for production use

---

## 📊 Dataset

A synthetic datasets of 10,000 NFT trades was generated with features such as:
- `price`, `gas_fee`, `trade_size`
- `buyer_address`, `seller_address`
- `token_id`, `seller_reputation`
- Time features (e.g., hour of day, transaction frequency)

Wash trade were simulate by introducing pattern like:
- Same buyer and seller
- Abnormal price/gas fee spikes
- Lower reputation for suspected sellers

---

## 🧠 Machine Learning Approach

### Feature Engineering:
- TimeOfDay and frequency bins
- Address pair trade frequency
- Price volatility classification
- Polynomial interaction features

### Model Pipeline:
1. **StandardScaler** for normalization
2. **SMOTE** to address class imbalance
3. **Ensemble Model** using:
    - XGBoost (with hyperparameter tuning)
    - Random Forest
    - LightGBM

---

## ✅ Results

- **Accuracy**: 86%
- **F1-Score (wash trades)**: 0.69
- **ROC-AUC**: 0.92
- **PR AUC**: 0.74

📊 Confusion Matrix:

[[1414 176]
[ 101 309]]

---

## 📦 Files

NFT_Wash_Trade/
├── NFT_Wash_Trade.ipynb # Jupyter notebook with code and evaluation
├── wash_trade_model.pkl # Trained model file
├── scaler.pkl # StandardScaler used for inference
├── requirements.txt # Python dependencies
└── README.md # Project documentation


---

## 💡 Future Ideas

- Apply the same logic to real NFT datasets (e.g., OpenSea, Ethereum logs)
- Explore network graph-based features (e.g., address graph)
- Deploy with Streamlit or FastAPI for live predictions

---

## 📌 How to Use

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt

Open NFT_Wash_Trade.ipynb to explore, train, or test the model

Use wash_trade_model.pkl and scaler.pkl for inference

📜 License
This project is for educational and portfolio use only.


