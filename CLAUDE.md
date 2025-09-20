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
│   ├── raw/                       # Raw ProZorro API responses
│   ├── processed/                 # Cleaned and feature-engineered data
│   └── external/                  # Company registries, geographic data
├── notebooks/                     # Jupyter notebooks for research
│   ├── 01_data_exploration.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_model_comparison.ipynb
│   ├── 04_regional_analysis.ipynb
│   └── 05_pattern_discovery.ipynb
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
    ├── data_collection.py
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

- **ProZorro API** - Primary source for tender data (4M+ records)
- **State Registry of Legal Entities** - Company information
- **Geographic boundaries** - Administrative divisions of Ukraine
- **Historical corruption cases** - For supervised learning validation

## Research Methodology

### Phase 1: Data Collection & Exploration
- Systematic download of ProZorro data (2020-2024)
- Exploratory data analysis to understand patterns
- Domain research on procurement fraud schemes
- Data quality assessment and cleaning

### Phase 2: Feature Engineering & Model Development  
- Price anomaly detection (regional/seasonal baselines)
- Competition analysis (participant count, bidding behavior)
- Network features (company connections, market concentration)
- Temporal features (deadline pressure, budget cycles)
- Text analysis (technical specification similarity)

### Phase 3: Model Comparison & Evaluation
- Benchmark multiple ML approaches on labeled data
- Cross-validation strategies for temporal data
- Feature importance analysis across models
- Explainability framework development

### Phase 4: Pattern Analysis & Insights
- Unsupervised clustering for fraud scheme taxonomy
- Regional and temporal trend analysis
- Network analysis for company relationship mapping
- Policy recommendations based on findings

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
- **Taxonomy of fraud schemes** in Ukrainian procurement
- **Quantitative analysis** of corruption patterns
- **Regional and temporal trends** identification
- **Policy recommendations** for procurement reform

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

# Set up .NET API
cd src/api
dotnet restore
dotnet build

# Set up React frontend
cd ../frontend
npm install
npm run dev
```

### Data Collection
```bash
# Download initial dataset
python scripts/data_collection.py --start-date 2020-01-01 --end-date 2024-12-31

# Process and clean data
python scripts/data_processing.py --input data/raw --output data/processed
```

### Model Training
```bash
# Run feature engineering
python src/ml/feature_engineering.py

# Train and evaluate models
python src/ml/model_training.py --config configs/experiment_1.yaml

# Generate analysis reports
python src/ml/batch_analysis.py --region all --period 2024
```

## Contributing

This is an academic research project. Contributions welcome in the form of:
- Code improvements and bug fixes
- Additional feature engineering ideas
- Validation of methodology and results
- Documentation enhancements

## License

MIT License - Open source for academic and research purposes

---

*This project is part of a Master's thesis in Computer Science, focusing on the application of machine learning techniques to public procurement transparency and corruption detection in Ukraine.*