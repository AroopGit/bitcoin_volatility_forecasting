# Bitcoin Realized Volatility Forecasting

## Overview

This project implements advanced forecasting models to predict Bitcoin's 7-day average daily realized volatility using both traditional econometric approaches (GARCH family models) and modern deep learning techniques (LSTM neural networks).

## Project Structure

```
bitcoin_foreacasting_model/
├── notebooks/
│   ├── exploratory-book1.ipynb    # Initial data exploration and baseline models
│   ├── exploratory-book2.ipynb    # GARCH models and basic LSTM implementations
│   └── final_notebook.ipynb       # Comprehensive analysis and final optimized models
└── README.md
```

## Key Features

- **Multi-Model Approach**: Compares traditional GARCH models with state-of-the-art LSTM networks
- **Comprehensive Validation**: Implements rolling window validation for robust out-of-sample testing
- **Feature Engineering**: Advanced technical indicators and derived features
- **Hyperparameter Optimization**: Systematic search for optimal model configurations
- **Performance Benchmarking**: Clear metrics and comparison framework

## Methodology

### Data Collection
- **Source**: Yahoo Finance API (`yfinance`)
- **Period**: September 2014 - August 2021 (~2,500 trading days)
- **Features**: OHLC price data for Bitcoin (BTC-USD)

### Volatility Calculation
Realized volatility is calculated as the standard deviation of log returns over specific interval windows, following established financial econometrics practices.

### Model Architecture

#### Traditional Models
- **Baseline Models**: Mean reversion and random walk approaches
- **GARCH Family**: GARCH(1,1), GJR-GARCH, TARCH models with asymmetric effects
- **Bootstrap GARCH**: Enhanced with bootstrapping for robustness

#### Deep Learning Models
- **Univariate LSTM**: Single and bidirectional architectures
- **Multivariate LSTM**: Enhanced with technical indicators
- **Hybrid Models**: LSTM with convolutional layers for feature extraction

### Performance Metrics
- **RMSPE** (Root Mean Squared Percentage Error): Primary metric
- **RMSE** (Root Mean Square Error): Secondary metric
- **Validation Strategy**: 70% training, 15% validation, 15% testing split

## Results

| Model Type | Validation RMSPE | Improvement |
|------------|------------------|-------------|
| Baseline (Mean) | 0.201 | - |
| Random Walk | 0.201 | - |
| TARCH(1,2) | 0.201 | - |
| Univariate LSTM | 0.164 | 18.4% |
| **Final Multivariate LSTM** | **0.157** | **21.9%** |

## Key Findings

1. **LSTM Superiority**: Neural networks significantly outperform traditional GARCH models
2. **Bidirectional Processing**: Enhanced architectures show better performance
3. **Feature Engineering**: Multivariate models improve forecasting accuracy
4. **Volatility Clustering**: Confirmed presence of volatility persistence effects
5. **Asymmetric Effects**: Negative price movements have larger volatility impact

## Requirements

### Core Dependencies
```
numpy>=1.15
pandas>=0.24
matplotlib>=3.0
seaborn>=0.9
scipy>=1.0
scikit-learn>=0.20
```

### Financial Analysis
```
yfinance>=0.1.63
arch>=4.0
statsmodels>=0.10
```

### Deep Learning
```
tensorflow>=2.0
keras>=2.0
talos>=1.0
```

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd bitcoin_foreacasting_model
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run Jupyter notebooks:
```bash
jupyter notebook notebooks/
```

## Usage

1. **Start with `exploratory-book1.ipynb`** for data exploration and baseline models
2. **Continue with `exploratory-book2.ipynb`** for GARCH models and basic LSTM
3. **Complete with `final_notebook.ipynb`** for comprehensive analysis and final models

## Applications

This research has practical applications in:
- **Risk Management**: Portfolio risk assessment and VaR calculations
- **Option Trading**: Volatility-based trading strategies
- **Portfolio Optimization**: Dynamic allocation based on volatility forecasts
- **Market Making**: Bid-ask spread adjustments

## Technical Notes

- **Data Frequency**: Daily OHLC data
- **Forecast Horizon**: 7-day average daily volatility
- **Validation Period**: Rolling window approach
- **Computational Requirements**: GPU recommended for LSTM training

## Contributing

This is a research project demonstrating advanced financial modeling techniques. For questions or contributions, please refer to the methodology and implementation details in the notebooks.

## License

This project is for educational and research purposes. Please ensure compliance with relevant data usage policies and financial regulations when applying these models in practice.

## Acknowledgments

- Yahoo Finance for providing market data
- The financial econometrics community for GARCH model foundations
- The deep learning community for LSTM implementations

---

*This project demonstrates the evolution from traditional econometric models to modern deep learning approaches in financial time series forecasting.* 