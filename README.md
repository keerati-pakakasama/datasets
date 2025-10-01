# P-COLD Database (China) - Operational Risk Analysis Repository

The **P-COLD Database (Public-Chinese Operational Loss Data)** is a cross-institutional operational risk loss event dataset spanning **1986–2023**, containing **3,723 labeled records**. It was compiled from publicly reported events using automated text mining methods and is available through the Figshare data repository.

This dataset represents **one of the largest and most comprehensive external operational risk databases in China**, offering unique opportunities for research in operational risk management, machine learning applications, and Basel II/III regulatory compliance analysis.

---

## Dataset Overview

### Key Statistics
- **Time Coverage:** 1986–2023 (37 years)
- **Number of Records:** 3,723 loss events  
- **Data Type:** Publicly reported operational loss events from Chinese banking sector
- **Scope:** Cross-institutional, China-focused dataset
- **Data Collection Method:** Automated text mining from major Chinese financial news websites
- **Languages:** Both Chinese and English versions available

### Database Structure (12 Key Fields)

| Field | Description | Data Type | Basel II Classification |
|-------|-------------|-----------|-------------------------|
| **Occurrence Time** | Event start date | Date | Core temporal data |
| **End Time** | Event resolution date | Date | Duration analysis |
| **Loss Amount** | Monetary value of operational loss | Numeric (CNY) | Severity measure |
| **Bank Involved** | Financial institution affected | Categorical | Institutional analysis |
| **Province Occurred** | Geographic location (province) | Categorical | Regional risk mapping |
| **City Occurred** | Geographic location (city) | Categorical | Urban risk analysis |
| **Person Involved** | Individual(s) associated with event* | Text | Human factor analysis |
| **Causal Factor** | Primary driver of loss event | Categorical | Risk attribution |
| **Event Type** | Basel II event classification | Categorical | Regulatory categorization |
| **Business Line** | Basel II business line classification | Categorical | Business risk segmentation |
| **Event Headline** | News headline text | Text | Text mining source |
| **Event Text** | Full news article content | Text | Detailed context |

*Note: Due to privacy protection, some sensitive fields may have limited disclosure.

---

## Data Access & Citation

### Download Instructions
📥 **To obtain the P-COLD dataset:**

1. **Visit Figshare Repository:** [https://figshare.com/articles/dataset/A_cross-institutional_database_of_operational_risk_external_loss_events_in_Chinese_banking_sector_1986-2023/23940069](https://figshare.com/articles/dataset/A_cross-institutional_database_of_operational_risk_external_loss_events_in_Chinese_banking_sector_1986-2023/23940069)
2. **Download Files:**
   - `P-COLD-English_ver.xlsx` (English version - recommended)
   - `P-COLD-Chinese_ver.xlsx` (Chinese version - optional)
   - `Data_dictionary.xlsx` (Field definitions - essential)
3. **Place in Repository:** Save files to `data/raw/` folder in this repository
4. **File Size:** Approximately 511 kB total

### Academic Publication
- **Nature Scientific Data Article:** [https://www.nature.com/articles/s41597-024-03803-1](https://www.nature.com/articles/s41597-024-03803-1)

### Citation
```bibtex
@article{zhu2024cross,
  title={A cross-institutional database of operational risk external loss events in Chinese banking sector 1986–2023},
  author={Zhu, Xiaolin and Chang, Yichen and Li, Jiahui},
  journal={Scientific Data},
  volume={11},
  number={1},
  pages={939},
  year={2024},
  publisher={Nature Publishing Group},
  doi={10.1038/s41597-024-03803-1}
}
```

---

## Basel II Operational Risk Framework

### Seven Event Types (Level 1 Classification)
1. **Internal Fraud** - Misappropriation of assets, tax evasion, bribery
2. **External Fraud** - Theft of information, hacking, third-party fraud  
3. **Employment Practices and Workplace Safety** - Discrimination, workers compensation
4. **Clients, Products, and Business Practices** - Market manipulation, product defects, fiduciary breaches
5. **Damage to Physical Assets** - Natural disasters, terrorism, vandalism
6. **Business Disruption and System Failures** - Utility disruptions, software/hardware failures
7. **Execution, Delivery, and Process Management** - Data entry errors, failed reporting, negligent asset loss

### Eight Business Lines
1. Corporate Finance
2. Trading & Sales  
3. Retail Banking
4. Commercial Banking
5. Payment & Settlement
6. Agency Services
7. Asset Management
8. Retail Brokerage

---

## Repository Structure

```
datasets/P-COLD_Database_(China)/
├── data/
│   ├── raw/
│   │   ├── P-COLD-English_ver.xlsx         # 📥 DOWNLOAD: English version
│   │   ├── P-COLD-Chinese_ver.xlsx         # 📥 DOWNLOAD: Chinese version  
│   │   └── Data_dictionary.xlsx            # 📥 DOWNLOAD: Field definitions
│   ├── processed/
│   │   ├── cleaned_data.csv               # Processed dataset for analysis
│   │   ├── feature_engineered.csv         # Enhanced dataset with derived features
│   │   └── time_series_data.csv           # Time-indexed event data
│   └── external/
│       └── basel_ii_classifications.csv   # Reference classifications
├── notebooks/
│   ├── 01_data_exploration.ipynb          # Initial data review and profiling
│   ├── 02_data_quality_assessment.ipynb   # Missing values and outlier analysis  
│   ├── 03_temporal_analysis.ipynb         # Time series patterns and trends
│   ├── 04_geographic_analysis.ipynb       # Regional risk distribution
│   ├── 05_loss_severity_modeling.ipynb    # Statistical distribution fitting
│   ├── 06_frequency_analysis.ipynb        # Event frequency modeling
│   ├── 07_machine_learning_models.ipynb   # Predictive modeling experiments
│   └── 08_regulatory_capital_calc.ipynb   # Basel II capital requirement estimation
├── src/
│   ├── data_preprocessing.py              # Data cleaning utilities
│   ├── feature_engineering.py             # Feature creation functions
│   ├── statistical_models.py              # Loss distribution models
│   ├── visualization.py                   # Plotting utilities
│   └── ml_models.py                      # Machine learning implementations
├── results/
│   ├── figures/                          # Generated plots and charts
│   ├── models/                           # Trained model artifacts
│   └── reports/                          # Analysis summary reports
├── docs/
│   ├── basel_ii_framework.md             # Regulatory background
│   ├── data_dictionary.md                # Field definitions and coding
│   ├── methodology.md                    # Analysis approach documentation  
│   ├── download_instructions.md          # Dataset download guide
│   └── references.bib                    # Academic references
└── README.md                             # This file
```

---

## Analysis Plan Overview

### **Key Research Questions**
1. **Risk Distribution:** How are operational losses distributed across event types and business lines?
2. **Temporal Patterns:** What trends exist in Chinese operational risk over 37 years (1986-2023)?
3. **Geographic Concentration:** Which regions and cities show highest operational risk exposure?
4. **Predictive Modeling:** Can machine learning models forecast operational risk events?
5. **Regulatory Capital:** How do Basel II capital requirements vary across institutions?

### **Statistical Characteristics (from Literature)**
- **Loss Severity:** High peak (kurtosis: 3,088) and fat tail (skewness: 54) distributions
- **Loss Frequency:** Negative binomial distribution provides best fit across all categories
- **Dispersion:** Standard deviation of 704,614 CNY indicates high variability typical of operational risk

### **Recommended Analysis Workflow**
1. **Data Quality Assessment** → Missing values, outliers, validation checks
2. **Exploratory Data Analysis** → Distributions, correlations, temporal patterns  
3. **Statistical Modeling** → Loss severity and frequency distribution fitting
4. **Machine Learning** → Classification, regression, and forecasting models
5. **Regulatory Analysis** → Basel II capital calculation and stress testing

---

## Getting Started

### **Prerequisites**
```python
# Required Python packages for analysis
pandas>=1.5.0          # Data manipulation and analysis
numpy>=1.21.0           # Numerical computing  
matplotlib>=3.5.0       # Basic plotting and visualization
seaborn>=0.11.0         # Statistical data visualization
plotly>=5.0.0           # Interactive charts and maps
scikit-learn>=1.1.0     # Machine learning algorithms
scipy>=1.8.0            # Statistical functions and tests
statsmodels>=0.13.0     # Time series analysis and regression
geopandas>=0.11.0       # Geographic data analysis for China maps
openpyxl>=3.0.0         # Excel file reading (.xlsx format)
```

### **Installation Commands**
```bash
# Install required packages
pip install pandas numpy matplotlib seaborn plotly scikit-learn scipy statsmodels geopandas openpyxl

# Or use conda
conda install pandas numpy matplotlib seaborn plotly scikit-learn scipy statsmodels geopandas openpyxl
```

### **Quick Start Checklist**
- [ ] **Download dataset** from Figshare and place in `data/raw/`
- [ ] **Install Python packages** listed above
- [ ] **Run `01_data_exploration.ipynb`** to understand the dataset structure
- [ ] **Execute `02_data_quality_assessment.ipynb`** to identify data issues
- [ ] **Continue with analysis notebooks** in numbered sequence

---

## Expected Deliverables

### **Analysis Outputs**
1. **Data Quality Report** - Completeness assessment and cleaning recommendations
2. **Statistical Analysis Report** - Distribution fitting and descriptive statistics
3. **Temporal Analysis Report** - Trend identification and time series modeling
4. **Geographic Risk Atlas** - Province and city-level risk mapping
5. **Machine Learning Models** - Trained models for prediction and classification
6. **Regulatory Capital Calculator** - Basel II capital requirement estimation tool

### **Research Applications**
- **Academic Research:** Operational risk modeling for emerging markets
- **Industry Practice:** Risk management benchmarking and peer analysis
- **Regulatory Compliance:** Basel II/III implementation and validation
- **Policy Development:** Evidence-based financial regulation recommendations

---

## Contributing & Support

### **Contribution Areas**
- Additional analysis notebooks and methodologies
- Enhanced visualization techniques
- Advanced machine learning implementations
- Regulatory framework updates
- Documentation improvements

### **Data Science Best Practices**
- Follow reproducible research principles
- Document all assumptions and limitations
- Version control analysis code and results
- Validate findings with multiple approaches
- Cite original data sources appropriately

---

## License & Disclaimer

### **Usage Rights**
This repository and analysis framework are available for **research and educational purposes**. The P-COLD dataset is subject to the terms and conditions specified by the original authors and Figshare repository under CC BY 4.0 License.

### **Limitations & Warnings**
⚠️ **Important Considerations:**
- Data represents publicly reported events only (potential underreporting bias)
- Automated text mining may introduce classification errors  
- External loss data may not reflect internal risk profiles accurately
- Results should not be used for commercial risk assessment without validation
- Privacy-sensitive fields have been anonymized or excluded

### **Research Ethics**
- Respect data privacy and anonymization measures
- Acknowledge limitations of external loss data in publications
- Follow institutional review board requirements for human subjects research
- Cite original data sources and methodology papers appropriately

---

## Credits & Acknowledgments

### **Analysis Framework Development**
This comprehensive README.md and analysis framework was developed with assistance from **Perplexity AI Research Agent** (powered by Claude) in October 2025. The framework includes:

- **Research Integration:** Comprehensive literature review and synthesis of operational risk modeling approaches
- **Basel II Framework:** Detailed regulatory compliance methodology and capital calculation procedures  
- **Machine Learning Applications:** Predictive modeling recommendations based on current ML practices in finance
- **Statistical Analysis Plan:** Evidence-based analytical approaches validated against academic publications
- **Repository Structure:** Data science best practices for reproducible research

### **Data Source Attribution**
- **Original Dataset:** P-COLD Database created by Zhu, X., Chang, Y., & Li, J. (2024)
- **Publication:** *Scientific Data*, 11(1), 939. https://doi.org/10.1038/s41597-024-03803-1
- **Repository:** Figshare. https://figshare.com/articles/dataset/A_cross-institutional_database_of_operational_risk_external_loss_events_in_Chinese_banking_sector_1986-2023/23940069

### **Research Methodology References**
The analysis recommendations are grounded in peer-reviewed publications and regulatory guidelines:
- Basel Committee on Banking Supervision operational risk frameworks
- Machine learning applications in financial risk management (ORX, 2024)
- Statistical modeling approaches for operational loss data (Nature Scientific Data, 2024)
- Advanced measurement approaches for regulatory capital calculation

### **Disclaimer**
The AI-generated analysis framework provides research guidance and methodological recommendations. Users should validate all approaches against current regulatory requirements and institutional policies. The framework is intended for educational and research purposes.

---

**Documentation Version:** 1.0  
**Last Updated:** October 1, 2025  
**Framework Contributors:** Data Engineering Team + AI Research Assistant  
**Dataset Source:** Zhu et al. (2024) via Figshare under CC BY 4.0 License
