# MLOps End-to-End ML Pipeline using DVC and AWS S3

This project demonstrates an end-to-end Machine Learning Operations (MLOps) pipeline utilizing Data Version Control (DVC) and Amazon Web Services (AWS) S3 for efficient data and model management.

## Project Overview

The pipeline encompasses the complete lifecycle of a machine learning project, including:

1. **Data Ingestion**: Collecting and storing raw data.
2. **Data Versioning**: Using DVC to version control datasets, ensuring reproducibility and traceability.
3. **Data Storage**: Leveraging AWS S3 buckets to store raw and processed data.
4. **Model Training**: Training machine learning models using versioned data.
5. **Model Versioning**: Managing different model versions with DVC.
6. **Model Deployment**: Deploying models for inference.
7. **Model Monitoring**: Continuously monitoring model performance and data drift.

## Repository Structure

- `.dvc/`: Contains DVC-specific files for tracking data versions and pipeline stages.
- `dvclive/`: Stores metrics and logs generated during model training and evaluation.
- `experiments/`: Directory for conducting and tracking various experiments.
- `src/`: Source code for data processing, model training, and evaluation.
- `.dvcignore`: Specifies files and directories for DVC to ignore.
- `.gitignore`: Specifies files and directories for Git to ignore.
- `LICENSE`: The project's license file.
- `README.md`: This file, providing an overview of the project.
- `dvc.lock`: Locks the versions of data and pipelines, ensuring consistency.
- `dvc.yaml`: Defines the stages of the pipeline and their dependencies.
- `params.yaml`: Contains hyperparameters and other configuration settings.
- `projectflow.txt`: Describes the flow and stages of the project.
- `template.py`: A template script for various tasks.

## Key Features

- **Data Versioning with DVC**: Ensures that datasets are versioned and changes are tracked over time, facilitating reproducibility.
- **AWS S3 Integration**: Utilizes AWS S3 buckets to store and retrieve data, providing scalable and reliable storage solutions.
- **Pipeline Orchestration**: Automates the workflow from data ingestion to model deployment using DVC pipelines.
- **Experiment Tracking**: Manages and compares different experiments to identify the best-performing models.
- **Continuous Monitoring**: Implements monitoring to detect data drift and maintain model performance over time.

## Getting Started

### Prerequisites

- Python 3.x installed on your system.
- AWS account with configured credentials for accessing S3.
- DVC installed with S3 support:

  ```bash
  pip install 'dvc[s3]'
  ```

### Installation

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/Anand21J-V/MLOPs-End-to-End-ML-Pipeline-using-DVC-and-AWS-S3.git
   cd MLOPs-End-to-End-ML-Pipeline-using-DVC-and-AWS-S3
   ```

2. **Initialize DVC**:

   ```bash
   dvc init
   ```

3. **Configure AWS S3 Remote**:

   ```bash
   dvc remote add -d myremote s3://your-s3-bucket-name
   ```

   Replace `your-s3-bucket-name` with your actual S3 bucket name.

4. **Pull Data from S3**:

   ```bash
   dvc pull
   ```

   This command retrieves the versioned data from the configured S3 bucket.

5. **Install Required Python Packages**:

   ```bash
   pip install -r requirements.txt
   ```

### Running the Pipeline

To execute the entire pipeline:

```bash
dvc repro
```

This command will run all the stages defined in `dvc.yaml`, from data preprocessing to model evaluation.

### Monitoring Experiments

DVC integrates with various experiment tracking tools. Ensure that the `dvclive` directory is properly set up to log metrics during training. You can visualize these metrics using your preferred tool.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Author

Anand Vishwakarma

---
