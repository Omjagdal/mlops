# MLOps Project: Model Training and Deployment Pipeline

## Overview
This project demonstrates a complete MLOps pipeline for training, versioning, and deploying a machine learning model. It includes automated training, model registry, API deployment, and monitoring capabilities.

## Features
- Automated model training pipeline
- Model versioning and registry with MLflow
- REST API for model predictions
- Docker containerization
- CI/CD integration
- Model performance monitoring
- Data drift detection

## Project Structure
```
mlops-project/
├── data/
│   ├── raw/
│   └── processed/
├── models/
├── notebooks/
│   └── exploratory_analysis.ipynb
├── src/
│   ├── data/
│   │   ├── preprocessing.py
│   │   └── validation.py
│   ├── models/
│   │   ├── train.py
│   │   └── predict.py
│   └── monitoring/
│       └── drift_detection.py
├── api/
│   ├── app.py
│   └── schemas.py
├── tests/
├── Dockerfile
├── requirements.txt
├── config.yaml
└── README.md
```

## Requirements
- Python 3.9+
- Docker
- MLflow
- FastAPI
- scikit-learn
- pandas
- numpy

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/mlops-project.git
cd mlops-project
```

2. Create virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

### Training the Model
```bash
python src/models/train.py --config config.yaml
```

### Running the API
```bash
uvicorn api.app:app --host 0.0.0.0 --port 8000
```

### Using Docker
```bash
docker build -t mlops-model:latest .
docker run -p 8000:8000 mlops-model:latest
```

### Making Predictions
```bash
curl -X POST "http://localhost:8000/predict" \
     -H "Content-Type: application/json" \
     -d '{"features": [5.1, 3.5, 1.4, 0.2]}'
```

## Model Monitoring
Access MLflow UI for experiment tracking:
```bash
mlflow ui --port 5000
```

## Testing
```bash
pytest tests/
```

## CI/CD
This project uses GitHub Actions for continuous integration. The pipeline automatically runs tests and builds Docker images on every push to main.

## Configuration
Edit `config.yaml` to customize training parameters, model settings, and deployment configurations.
