[ Dataset: CICIDS2017 / CICIoT2023 ]
            │
            ▼
[ Stage 1: Data Preprocessing ]
  ├── Drop metadata columns (Source/Dest IP, Ports, Timestamp, Flow ID)
  └── Impute missing and infinite values (np.inf -> np.nan -> median)
            │
            ▼
[ Stage 2: Data Pipeline & Splitting ]
  ├── 80/20 Stratified Train-Test Split (Execute BEFORE scaling/oversampling)
  ├── MinMaxScaler fitting (Applied strictly on Training Set)
  └── SMOTE Class Balancing (Applied strictly on Training Set)
            │
            ▼
[ Stage 3: Model Training Engine ]
  └── Train XGBoost, Random Forest, and LightGBM Classifiers
            │
            ▼
[ Stage 4: Performance Evaluation ]
  └── Compute Precision, Recall, Macro-F1, FPR, Confusion Matrices
            │
            ▼
[ Stage 5: Explainable AI (XAI) Integration ]
  ├── SHAP TreeExplainer (Global feature attribution & importance ranking)
  └── LIME Instance Explainer (Local packet-level decision breakdowns)
            │
            ▼
[ Output: IEEE Manuscript, Thesis Book, GitHub Codebase ]
