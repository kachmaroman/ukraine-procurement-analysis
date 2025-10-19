# Ukrainian Procurement Anomaly Analysis

## Project Overview

**Research Topic:** "Research on Methods for Analyzing Anomalies in Public Procurement Using Machine Learning"  
**Original Title (Ukrainian):** "Дослідження методів аналізу аномалій у державних закупівлях з використанням машинного навчання"

This is a Master's thesis project focused on analyzing corruption patterns in Ukrainian public procurement using machine learning techniques. The goal is to create comprehensive "information portraits" of anomalies rather than simple binary classification.

## Research Objectives

- **Primary Goal:** Develop open-source methodology for procurement fraud pattern analysis
- **Academic Contribution:** Benchmark different ML approaches on Ukrainian ProZorro data
- **Practical Impact:** Create analytical tools for investigators, journalists, and civil society
- **Innovation:** Explainable AI approach vs existing black-box systems (DOZORRO)

## Project Structure

```
ukraine-procurement-analysis/
├── data/                          # Data processing and storage
│   ├── raw/                       # Raw Kaggle dataset files
│   │   ├── Suppliers.csv
│   │   └── Competitive_procurements.csv
│   ├── processed/                 # Cleaned and feature-engineered data
│   └── external/                  # Company registries, geographic data (optional)
├── notebooks/                     # Jupyter notebooks for research
│   ├── 01_initial_data_exploration.ipynb
│   ├── 02_deep_eda.ipynb
│   ├── 03_competition_analysis.ipynb
│   ├── 04_geographic_patterns.ipynb
│   ├── 05_price_anomalies.ipynb
│   ├── 06_feature_engineering.ipynb
│   ├── 07_model_comparison.ipynb
│   ├── 08_regional_analysis.ipynb
│   └── 09_pattern_discovery.ipynb
├── src/                          # Production code
│   ├── ml/                       # Machine learning pipeline
│   │   ├── data_processing.py
│   │   ├── feature_engineering.py
│   │   ├── models.py
│   │   ├── evaluation.py
│   │   └── explainability.py
│   ├── api/                      # .NET Core Web API
│   │   ├── Controllers/
│   │   ├── Services/
│   │   └── Models/
│   └── frontend/                 # React application
│       ├── src/components/
│       │   ├── InteractiveMap/
│       │   ├── Analytics/
│       │   └── TenderDetails/
│       └── src/services/
├── ml-service/                   # Python FastAPI ML service
│   ├── main.py
│   ├── models/
│   └── utils/
├── docs/                         # Documentation and research outputs
│   ├── methodology.md
│   ├── findings/
│   └── visualizations/
└── scripts/                      # Utility scripts
    ├── data_processing.py
    ├── batch_processing.py
    └── model_training.py
```

## Technology Stack

### Data Science & ML
- **Python 3.11+** - Primary ML development
- **pandas, numpy** - Data manipulation
- **scikit-learn** - Classical ML algorithms
- **xgboost, lightgbm** - Advanced ML models
- **networkx** - Graph analysis for company networks
- **geopandas** - Geographic analysis
- **shap** - Explainable AI
- **plotly, folium** - Interactive visualizations

### Backend API
- **.NET 8.0** - Web API and business logic
- **Entity Framework Core** - Data access
- **PostgreSQL** - Primary database
- **Redis** - Caching
- **FastAPI** - Python ML service

### Frontend
- **React 18 + TypeScript** - User interface
- **Leaflet** - Interactive maps
- **Recharts** - Data visualizations
- **Tailwind CSS** - Styling

### Development Tools
- **Docker** - Containerization
- **Jupyter Lab** - Research notebooks
- **Git** - Version control
- **Claude Code** - AI-assisted development

## Key Features

### ML Analysis Pipeline
- **Multi-algorithm benchmarking** (Random Forest, XGBoost, Neural Networks, Isolation Forest)
- **Feature engineering** for procurement domain (price patterns, network analysis, temporal trends)
- **Unsupervised pattern discovery** for new fraud scheme detection
- **Explainable AI** with SHAP values and feature importance

### Information Portraits
- **Regional profiles** - corruption patterns by oblast/city
- **Category analysis** - sector-specific fraud schemes (roads, medical, IT)
- **Temporal patterns** - seasonal trends, war impact, budget cycles
- **Network analysis** - suspicious company connections and market concentration

### Interactive Visualization
- **Ukraine heat map** with color-coded risk levels by region
- **Drill-down capability** from oblast → city → specific tenders
- **Filter system** by category, time period, amount, anomaly type
- **Export functionality** for reports and further analysis

## Data Sources

- **Kaggle ProZorro Dataset (2015-2019)** - Primary data source
  - **Suppliers.csv** - 3,621,822 records of tender winners with organizer and supplier details
  - **Competitive_procurements.csv** - 2,313,168 records of all tender participants
  - Key columns: lot_id, dates, CPV codes, prices (initial/final), regions, organizer/supplier codes
  - **Major finding:** 30.3% of tenders have only single bidder (298,511 cases) - significant red flag
  
- **ProZorro API** (Optional supplement)
  - Fresh data collection for 2020-2024 period if time permits
  - War period analysis (before/after Feb 24, 2022)
  - Validation of methodology on recent data
  
- **Geographic boundaries** - Ukrainian administrative divisions for mapping
- **Historical corruption cases** - Known cases for validation (if available)

## Research Methodology

### Phase 1: Data Analysis & Understanding (Months 1-2)
- **Dataset acquisition:** Kaggle ProZorro dataset (2015-2019)
  - 3.6M supplier records + 2.3M procurement participant records
- **Initial exploration:** Data structure, coverage, quality assessment
- **Deep EDA:** 
  - Regional patterns analysis (which oblasts most problematic)
  - Category breakdown (CPV codes with highest anomaly rates)
  - Temporal trends (yearly evolution, seasonal patterns)
  - **Key discovery:** 30.3% single bidder rate - major corruption indicator
- **Domain research:** Understanding procurement fraud schemes and patterns

### Phase 2: Feature Engineering & Model Development (Months 2-3)
- **Price features:** Deviations from regional/category medians, initial vs final price changes
- **Competition features:** Participant count, market concentration, win rates
- **Network features:** Company connection graphs, centrality measures
- **Temporal features:** Deadline patterns, budget cycle correlations, seasonal effects
- **Geographic features:** Distance analysis, cross-region activity patterns

### Phase 3: Model Comparison & Evaluation (Month 4)
- Benchmark multiple ML approaches:
  - Unsupervised: Isolation Forest, LOF, K-means clustering
  - Supervised: Random Forest, XGBoost (on labeled anomalies)
  - Graph-based: Network analysis for company relationships
- Cross-validation strategies for temporal data
- Feature importance analysis across models
- Explainability framework with SHAP values

### Phase 4: Information Portrait Formation (Month 4-5)
- **Regional portraits:** Corruption patterns by oblast/city
- **Category portraits:** Sector-specific fraud schemes (construction, medical, IT)
- **Temporal portraits:** Pre-2022 vs 2022+ patterns (if fresh data collected)
- **Network portraits:** Suspicious company clusters and market concentration
- Interactive visualization development (Ukraine heat map)

### Phase 5: Validation & Documentation (Month 6)
- Results validation on known corruption cases
- Thesis writing and documentation
- Code documentation and reproducibility
- Presentation preparation

## Expected Outcomes

### Academic Deliverables
- **Master's thesis** with comprehensive methodology
- **Conference paper** on ML approaches to procurement fraud
- **Open dataset** of anonymized patterns for research community
- **Reproducible framework** for other countries

### Practical Tools
- **Interactive web application** for pattern exploration
- **API endpoints** for integration with existing systems
- **Report generation** for investigators and journalists
- **Educational materials** on fraud detection techniques

### Research Insights
- **Major Discovery:** 30.3% single bidder tenders (298,511 cases) - far above normal 5-10%
- **Taxonomy of fraud schemes** in Ukrainian procurement (2015-2019)
- **Regional corruption patterns** and hotspot identification
- **Category-specific vulnerabilities** (construction, medical, IT sectors)
- **Temporal evolution** of corruption patterns across 5 years
- **Network analysis** of suspicious company clusters
- **Policy recommendations** for procurement reform based on empirical evidence

## Development Workflow

### Research Phase (Months 1-3)
- Data collection and exploratory analysis
- Literature review and methodology development
- Feature engineering and model experimentation
- Initial pattern discovery and validation

### Implementation Phase (Months 4-5)
- API development and ML service integration
- Frontend development with interactive maps
- System integration and testing
- User interface polish and optimization

### Documentation Phase (Month 6)
- Results analysis and interpretation
- Thesis writing and academic documentation
- Code documentation and deployment guides
- Presentation preparation and final testing

## Getting Started

### Prerequisites
- Python 3.11+
- .NET 8.0 SDK
- Node.js 18+
- PostgreSQL 15+
- Docker (optional)

### Initial Setup
```bash
# Clone repository
git clone https://github.com/username/ukraine-procurement-analysis
cd ukraine-procurement-analysis

# Set up Python environment
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt

# Create necessary directories
mkdir -p data/{raw,processed,external}
mkdir -p notebooks
mkdir -p docs/findings
```

### Data Setup
```bash
# Download Kaggle dataset manually and place in data/raw/:
# - Suppliers.csv (3.6M records)
# - Competitive_procurements.csv (2.3M records)

# Or use Kaggle API:
kaggle datasets download -d oleksastepaniuk/prozorro-public-procurement-dataset
unzip prozorro-public-procurement-dataset.zip -d data/raw/
```

### Initial Data Exploration
```bash
# Launch Jupyter Lab
jupyter lab

# Open notebooks/01_initial_data_exploration.ipynb
# Run initial analysis to understand data structure
```

## Contributing

This is an academic research project. Contributions welcome in the form of:
- Code improvements and bug fixes
- Additional feature engineering ideas
- Validation of methodology and results
- Documentation enhancements

## License

MIT License - Open source for academic and research purposes

## Contact

**Student:** [Your Name]  
**University:** [University Name]  
**Supervisor:** [Supervisor Name]  
**Email:** [your.email@university.edu]

---

*This project is part of a Master's thesis in Computer Science, focusing on the application of machine learning techniques to public procurement transparency and corruption detection in Ukraine.*