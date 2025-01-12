# Useful commands

This project demonstrates an MLOps workflow using MLFlow and FastAPI on the EMNIST dataset. The project involves training a Convolutional Neural Network (CNN) with PyTorch, tracking experiments with MLFlow, and serving the trained model using FastAPI.

## Run MLFlow Tracking Server

```bash
mlflow server
```

## Run training script

```bash
python train_model.py <run_name>
```

To see script usage, run:

```bash
python train_model.py --help
```

## Run model serving API

```bash
uvicorn serving:app --reload
```

## Request model serving API

```bash
curl -X POST http://127.0.0.1:8000/predict -F "file=@data/test_image.jpg"
```

## Project Overview

1. **Training a CNN on EMNIST**: The project includes a script to train a CNN on the EMNIST dataset using PyTorch. The training process is tracked using MLFlow, which logs parameters, metrics, and the trained model.
2. **Experiment Tracking with MLFlow**: Each training run is tracked by MLFlow, allowing you to compare different runs and their results. Parameters and metrics are logged for each run.
3. **Model Registry**: The best model from the training runs is registered in the MLFlow Model Registry, allowing for versioning and easy deployment.
4. **Model Serving with FastAPI**: The trained model is served using a FastAPI application, which provides an endpoint to make predictions on new data.

### Prerequisites

1. **Install Python 3.11.7**: Ensure you have Python 3.11.7 installed, as MLFlow is not yet compatible with Python 3.12.x.
2. **Create a Virtual Environment**: Use `pyenv` to manage Python versions and create a virtual environment for the project.
3. **Install Dependencies**: Install the required Python packages listed in `requirements.txt`.

### Experiment Tracking and Model Registry with MLFlow

1. **Track Training Runs**: Each training run is tracked by MLFlow, logging parameters, metrics, and the trained model.
2. **Compare Runs**: Use the MLFlow dashboard to compare different training runs and their results.
3. **Register Models**: Register the best model in the MLFlow Model Registry for versioning and deployment.

### Model Serving with FastAPI

1. **Serve the Model**: Use FastAPI to serve the trained model, providing an endpoint to make predictions on new data.
2. **Make Predictions**: Use the provided `curl` command to send an image to the API and receive a prediction.

This project provides a complete MLOps workflow, from training and tracking experiments to serving the trained model using an API!