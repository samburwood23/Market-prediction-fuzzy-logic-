# Fuzzy Logic Analytics for Trading & Marketing

A comprehensive Python framework for predictive analytics using fuzzy logic systems, designed to maximize shareholder value through intelligent trading decisions and marketing optimization.

## Overview

This project implements advanced fuzzy logic inference systems for handling uncertainty in financial and marketing data. By combining linguistic variables, membership functions, and rule-based reasoning, the system provides actionable insights for:

- **Trading Analytics**: Price prediction, trend analysis, risk assessment, and portfolio optimization
- **Marketing Analytics**: Customer segmentation, campaign effectiveness, ROI prediction, and resource allocation
- **Shareholder Value**: Integration of both domains to maximize long-term shareholder returns

## Features

- **Fuzzy Logic Engine**: Complete implementation of Mamdani and Sugeno inference systems
- **Trading Indicators**: RSI, MACD, Bollinger Bands integrated with fuzzy reasoning
- **Marketing Metrics**: CLV, CAC, churn prediction with fuzzy classification
- **Shareholder Value Framework**: Multi-objective optimization combining trading and marketing insights
- **Visualization Tools**: Interactive dashboards for membership functions and rule outputs
- **Backtesting**: Historical simulation for strategy validation

## Installation
```bash
git clone https://github.com/yourusername/fuzzy-analytics.git
cd fuzzy-analytics
pip install -r requirements.txt
pip install -e .
```

## Quick Start

### Trading Analytics Example
```python
from fuzzy_analytics.trading import TradingFuzzySystem
from fuzzy_analytics.indicators import calculate_rsi, calculate_macd

# Initialize trading system
trading_system = TradingFuzzySystem()

# Analyze market conditions
price_data = [100, 102, 101, 103, 105, 104, 106]
rsi = calculate_rsi(price_data)
macd, signal = calculate_macd(price_data)

# Get trading recommendation
recommendation = trading_system.evaluate(
    rsi=rsi,
    macd_histogram=macd - signal,
    volatility=0.25
)

print(f"Trading Signal: {recommendation['action']}")
print(f"Confidence: {recommendation['confidence']:.2%}")
```

### Marketing Analytics Example
```python
from fuzzy_analytics.marketing import MarketingFuzzySystem

# Initialize marketing system
marketing_system = MarketingFuzzySystem()

# Evaluate campaign performance
result = marketing_system.evaluate_campaign(
    engagement_rate=0.45,
    conversion_rate=0.08,
    roi=2.3
)

print(f"Campaign Quality: {result['quality']}")
print(f"Recommended Action: {result['recommendation']}")
```

### Shareholder Value Integration
```python
from fuzzy_analytics.shareholder_value import ShareholderValueOptimizer

# Combine trading and marketing insights
optimizer = ShareholderValueOptimizer()

result = optimizer.calculate_value(
    trading_returns=15.0,
    marketing_roi=2.5,
    risk_level=30,
    market_share_growth=8.0
)

print(f"Shareholder Value Score: {result['shareholder_value_score']:.1f}/100")
print(f"Total Value Impact: {result['total_value_impact_percent']:.2f}%")
```

## Architecture
```
fuzzy-analytics/
├── src/fuzzy_analytics/
│   ├── core/              # Core fuzzy logic engine
│   ├── trading/           # Trading-specific modules
│   ├── marketing/         # Marketing-specific modules
│   ├── shareholder_value/ # Value optimization
│   ├── indicators/        # Technical indicators
│   └── utils/             # Utility functions
├── examples/              # Example implementations
├── tests/                 # Unit and integration tests
└── docs/                  # Additional documentation
```

## Fuzzy Logic Concepts

### Membership Functions
The system uses multiple membership function types:
- **Triangular**: Simple, efficient, good for symmetric concepts
- **Trapezoidal**: Represents ranges with flat tops
- **Gaussian**: Smooth transitions, natural distributions
- **Sigmoid**: S-curves for asymmetric transitions

### Inference Methods
- **Mamdani**: For interpretable rule-based systems
- **Sugeno**: For computational efficiency and optimization

### Defuzzification
- Centroid method (center of gravity)
- Bisector method
- Mean of Maximum (MOM)
- Smallest of Maximum (SOM)
- Largest of Maximum (LOM)

## Trading Strategies

### Momentum Strategy
Combines RSI, MACD, and price momentum using fuzzy rules to identify entry and exit points.

**Example Rules:**
- IF RSI is oversold AND MACD is bullish THEN signal is strong_buy
- IF RSI is overbought AND MACD is bearish THEN signal is strong_sell

### Mean Reversion
Uses Bollinger Bands and statistical measures with fuzzy logic to capture reversion opportunities.

### Risk-Adjusted Returns
Integrates Sharpe ratio and volatility metrics for position sizing and risk management.

## Marketing Optimization

### Customer Segmentation
Fuzzy clustering for identifying high-value customer segments based on RFM (Recency, Frequency, Monetary) analysis.

**Segments:**
- Champions: Recent, frequent, high-value customers
- Potential Loyalists: Good engagement, growth potential
- At Risk: Declining activity, needs intervention

### Campaign Allocation
Optimal budget distribution across channels using fuzzy multi-criteria decision making.

**Metrics:**
- Engagement Rate
- Conversion Rate
- ROI (Return on Investment)

### Churn Prevention
Predictive modeling with fuzzy inference for identifying at-risk customers and recommending interventions.

## Shareholder Value Metrics

The framework optimizes for:
- **Total Return**: Trading gains + marketing-driven revenue growth
- **Risk-Adjusted Performance**: Balancing returns with volatility
- **Sustainable Growth**: Long-term value creation over short-term gains
- **Capital Efficiency**: ROI across both trading and marketing investments

### Key Metrics
- **Sharpe Ratio**: Risk-adjusted returns
- **Value at Risk (VaR)**: Maximum expected loss
- **Economic Value Added (EVA)**: Profit minus cost of capital
- **ROIC**: Return on invested capital

## Examples

### Complete Workflow
```python
# 1. Trading Analysis
from fuzzy_analytics import TradingFuzzySystem, TradingIndicators

prices = [100, 102, 101, 103, 105, 104, 106, 108, 107, 109]
rsi = TradingIndicators.calculate_rsi(prices)
macd, signal, histogram = TradingIndicators.calculate_macd(prices)
volatility = TradingIndicators.calculate_volatility(prices)

trading = TradingFuzzySystem()
trade_result = trading.evaluate(rsi, histogram, volatility)

# 2. Marketing Analysis
from fuzzy_analytics import MarketingFuzzySystem, CustomerSegmentationSystem

marketing = MarketingFuzzySystem()
campaign_result = marketing.evaluate_campaign(
    engagement_rate=0.45,
    conversion_rate=0.08,
    roi=2.3
)

segmentation = CustomerSegmentationSystem()
customer_result = segmentation.segment_customer(
    recency_days=15,
    purchase_frequency=24,
    annual_spend=5000
)

# 3. Integrated Shareholder Value
from fuzzy_analytics import ShareholderValueOptimizer

optimizer = ShareholderValueOptimizer()
value_result = optimizer.calculate_value(
    trading_returns=18.5,
    marketing_roi=2.4,
    risk_level=35,
    market_share_growth=8.5
)

print(f"Overall Value Score: {value_result['shareholder_value_score']:.1f}/100")
for recommendation in value_result['recommendations']:
    print(f"  → {recommendation}")
```

## Testing
```bash
# Run all tests
pytest tests/ -v

# Run with coverage
pytest tests/ --cov=fuzzy_analytics --cov-report=html

# Run specific test file
pytest tests/test_fuzzy_analytics.py -v
```

## Documentation

- **README.md**: Project overview and quick start (this file)
- **METHODOLOGY.md**: Complete theory and methodology
- **CONTRIBUTING.md**: Guidelines for contributors
- **examples/**: Working code examples
- **docs/**: Additional documentation

## Use Cases

### 1. Algorithmic Trading
- Generate trading signals from multiple indicators
- Optimize portfolio allocation
- Manage risk dynamically
- Backtest strategies

### 2. Marketing Optimization
- Evaluate campaign effectiveness
- Segment customers intelligently
- Predict and prevent churn
- Optimize budget allocation

### 3. Executive Decision Making
- Integrate trading and marketing performance
- Optimize capital allocation
- Maximize shareholder returns
- Strategic planning

### 4. Risk Management
- Calculate risk-adjusted metrics
- Set position sizes dynamically
- Monitor Value at Risk
- Balance risk and return

## Contributing

We welcome contributions! Please see CONTRIBUTING.md for details.

Areas we'd love help with:
- Additional technical indicators
- New marketing metrics
- Performance optimizations
- More examples and tutorials
- Documentation improvements

### Development Setup
```bash
# Clone the repository
git clone https://github.com/yourusername/fuzzy-analytics.git
cd fuzzy-analytics

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install in development mode
pip install -e ".[dev]"

# Run tests
pytest tests/
```

## Requirements

- Python >= 3.8
- numpy >= 1.21.0
- matplotlib >= 3.5.0
- pandas >= 1.3.0
- scipy >= 1.7.0
- scikit-learn >= 1.0.0

## License

MIT License

Copyright (c) 2025 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Citation

If you use this framework in your research, please cite:
```bibtex
@software{fuzzy_analytics,
  title={Fuzzy Logic Analytics for Trading and Marketing},
  author={Your Name},
  year={2025},
  url={https://github.com/yourusername/fuzzy-analytics}
}
```

## Acknowledgments

- Built with fuzzy logic principles from Lotfi Zadeh's foundational work
- Inspired by practical needs in financial and marketing analytics
- Designed for transparency and interpretability in AI decision-making

## Support

- **Issues**: Report bugs via GitHub Issues
- **Discussions**: Join community discussions
- **Documentation**: Comprehensive docs in `/docs` directory
- **Examples**: See `/examples` for working code

## Roadmap

- [ ] Add more technical indicators (Stochastic, ATR, Ichimoku)
- [ ] Implement genetic algorithms for rule optimization
- [ ] Add real-time data integration
- [ ] Create web dashboard for visualization
- [ ] Add backtesting framework
- [ ] Expand marketing attribution models
- [ ] Add multi-objective optimization algorithms

## Contact

For questions or collaboration opportunities, please open an issue on GitHub or reach out via email.

---

**Made with ❤️ for data-driven decision making**
