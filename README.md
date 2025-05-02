# GitHub Actions CI/CD for ML Demo

This repository demonstrates how to implement CI/CD pipelines for machine learning projects using GitHub Actions and Hugging Face Spaces, where the model is deployed as an interactive gradio app.

![Streamlit App Interface](app\assets\app-preview.png)

## Investigated Features

- **Continuous Integration (CI):** Automatically test and validate code changes.
- **Continuous Deployment (CD):** Deploy models or applications to production environments, including Hugging Face Spaces.
- **Version Control:** Track changes and ensure reproducibility.
- **Automation:** Streamline workflows for ML development.
- **Model Versioning:** Automatically update and deploy new model versions.
- **Visualization:** Generate performance metrics and visualizations, such as confusion matrices and learning curves.
- **Pytorch CNN** Simple Pytorch CNN Architecture.


## Getting Started

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/github-actions-cicd-for-ml-demo.git
    cd github-actions-cicd-for-ml-demo
    ```

2. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Run the project:
    ```bash
    python main.py
    ```

## CI/CD Workflow

The repository includes a GitHub Actions workflow file located in `.github/workflows/ci-cd.yml`. This workflow:

1. Runs unit tests on every push or pull request.
2. Builds and packages the application.
3. Deploys the application and updated model to Hugging Face Spaces.

### Continuous Integration

- Automatically tests code changes and validates model performance.
- Generates evaluation metrics, including accuracy, precision, recall, and F1 score.
- Produces visualizations such as confusion matrices and learning curves.

### Continuous Deployment

- Deploys the updated model and application to Hugging Face Spaces.
- Uses the Hugging Face CLI to upload model files, application code, and results.
- Ensures the deployed application is always up-to-date with the latest changes.

## Model and Dataset

- **Model:** A neural network trained to classify handwritten digits (MNIST dataset).
- **Dataset:** The MNIST dataset, consisting of grayscale images of digits (0-9) with a resolution of 28x28 pixels.
- **Training Pipeline:** The model is trained using PyTorch, with metrics and visualizations generated during training.

![MNIST Digits](./app/assets/mnist-classes.png)

### Model Architecture

The model is a simple feedforward neural network implemented in PyTorch. It consists of the following layers:

1. **Input Layer:** Accepts 28x28 grayscale images flattened into a 784-dimensional vector.
2. **Hidden Layers:** Two fully connected layers with ReLU activation functions to introduce non-linearity.
3. **Output Layer:** A softmax layer with 10 output nodes, corresponding to the 10 digit classes (0-9).

The architecture is simplified for the purposes of this application.

## Streamlit App

The deployed application is an interactive Streamlit app that allows users to test the trained model by drawing digits or uploading images. The app provides real-time predictions and displays the confidence scores for each digit class.

### Features of the App

- **Digit Input:** Users can draw a digit or upload an image for classification.
- **Prediction Results:** Displays the predicted digit along with confidence scores.
- **Visualization:** Includes visual aids to help users understand the model's predictions.

![Streamlit App Interface](app\assets\app-preview.png)

## Folder Structure

```
github-actions-cicd-for-ml-demo/
├── .github/
│   └── workflows/
│       └── ci-cd.yml
├── app/
│   ├── app.py
│   └── README.md
├── model_development/
│   ├── train_model.py
│   └── model_architecture.py
├── model_reporting/
│   ├── confusion_matrix.png
│   ├── nn_acc_curve.png
│   ├── nn_loss_curve.png
│   └── nn_lr_curve.png
├── requirements.txt
└── README.md
```

## Deployment to Hugging Face

The application and model are deployed to Hugging Face Spaces. The deployment process includes:

1. Logging into Hugging Face CLI using a secure token.
2. Uploading the application files, model weights, and evaluation results.
3. Automatically building the environment and running the application on Hugging Face Spaces.

This ensures that the application is accessible online with the latest model and results.