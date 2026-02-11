# Interpretable Machine Learning for Asset Pricing

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status: Research](https://img.shields.io/badge/status-research-green.svg)]()

> A comprehensive framework for building interpretable machine learning models in asset pricing, resolving the traditional trade-off between predictive performance and model transparency.

## 📊 Overview

This project develops and evaluates interpretable ML models for predicting equity excess returns, achieving **14.77% R²** (4× improvement over linear models) while maintaining full model transparency through multiple explanation techniques.

**Key Findings:**
- Risk-free rate emerges as the dominant predictor across all models and economic regimes
- Crisis periods show stronger linear relationships (GFC: 4.93% R²) but poor cross-regime transferability
- Momentum and volatility effects demonstrate significant regime-dependent behavior
- Ensemble methods capture non-linear relationships that traditional models miss

## 🎯 Motivation

Traditional ML models in finance operate as "black boxes," limiting their adoption in regulated environments where transparency is mandatory. This framework demonstrates that competitive predictive accuracy and interpretability are not mutually exclusive.

## 📈 Results Summary

| Model | MSE | RMSE (bps) | R² | Improvement vs Linear |
|-------|-----|------------|----|-----------------------|
| Linear Regression | 314.61 | 17.73 | 3.40% | Baseline |
| **Random Forest** | **283.59** | **16.84** | **14.77%** | **+334%** |
| XGBoost | 292.76 | 17.11 | 11.98% | +252% |

## 🔬 Methodology

### Data
- **Time Period**: 1980-2024 (540 months)
- **Sample Size**: 35,560 companies
- **Features**: 46 firm-level characteristics
- **Source**: CRSP database

### Models
1. **Linear Regression** - Baseline benchmark
2. **Random Forest** - Best overall performance
3. **XGBoost** - Gradient boosting ensemble

### Interpretability Framework
- **SHAP (SHapley Additive exPlanations)** - Feature attribution
- **iSHAP** - Interaction-aware SHAP for tree models
- **LIME** - Local instance explanations
- **Permutation Feature Importance (PFI)** - Model-agnostic importance

### Regime Analysis
Economic regimes analyzed:
- Volcker era (1980-1989)
- Dot-com boom (1990-1999)
- Pre-GFC (2000-2007)
- Global Financial Crisis (2008-2009)
- Post-GFC QE (2010-2019)
- COVID + inflation (2020-present)

### Prerequisites
```bash
Python 3.8+
pip or conda
```

### Dependencies
```txt
numpy>=1.21.0
pandas>=1.3.0
scikit-learn>=1.0.0
xgboost>=1.5.0
shap>=0.41.0
lime>=0.2.0
matplotlib>=3.4.0
seaborn>=0.11.0
scipy>=1.7.0
```

## 🔑 Key Features

### ✅ Interpretability Methods
- **Multiple perspectives**: SHAP, LIME, PFI provide complementary insights
- **Regime-specific analysis**: Understand how relationships change across economic periods
- **Instance-level explanations**: LIME provides predictions for individual stocks
- **Interaction detection**: iSHAP captures feature interactions


**"Improving Interpretability in Machine Learning-Based Asset Pricing"**  
*Student ID: 3010952*  
University of Glasgow, Adam Smith Business School  
Supervised by Dr. Marco Ercolani  
August 2025

[📄 Read the full paper](docs/dissertation.pdf) *(add when available)*

### Citation

If you use this code in your research, please cite:
```bibtex
@mastersthesis{interpretable_ml_asset_pricing_2025,
  title={Improving Interpretability in Machine Learning-Based Asset Pricing},
  author={[Mayur Sethia]},
  year={2025},
  school={University of Glasgow},
  type={Master's Thesis},
  note={Supervised by Dr. Marco Ercolani}
}
```

**Note**: CRSP data requires institutional access and is not included in this repository.

## 🐛 Known Issues & Limitations

- **Data Access**: CRSP data requires institutional subscription
- **Computational Cost**: Random Forest training on full dataset takes ~2-3 hours
- **Performance Ceiling**: R² capped at ~15% due to inherent market noise
- **Regime Definition**: Economic regimes are manually defined, not algorithmically detected


## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Supervisor**: Dr. Marco Ercolani, University of Glasgow
- **Data Source**: CRSP (Center for Research in Security Prices)
- **Inspiration**: Gu, Kelly & Xiu (2020) - "Empirical Asset Pricing via Machine Learning"
- **Libraries**: scikit-learn, SHAP, LIME, XGBoost teams


**⭐ If you find this project useful, please consider giving it a star!**


*Last updated: January 2025*
