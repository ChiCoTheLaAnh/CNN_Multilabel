
# CNN_Multilabel

## Overview

This project implements a custom deep convolutional neural network (AdvancedCNN) for multi-label image classification. The architecture leverages stacked residual blocks to enable deep feature extraction while preserving gradient flow, specifically tailored for datasets with multiple labels per sample.

## Key Features

- **AdvancedCNN Architecture:**  
  Four stages of residual blocks are stacked, allowing the network to extract rich and deep features while maintaining stable gradients, which is crucial for effective multi-label classification.

- **Robust Data Pipeline:**  
  - Images are resized to 224×224 and normalized.
  - Augmentation includes RandomHorizontalFlip to increase generalization.
  - Stratified train/validation splitting ensures balanced label distribution across splits.
  - Hyperparameter optimization with Adam optimizer, ReduceLROnPlateau learning rate scheduling, and early stopping to mitigate class imbalance and overfitting.

- **Performance:**  
  - Achieved a macro mAP (mean Average Precision) of **0.9604** on the test set.
  - Per-class F1 scores ≥ 0.90 for 8 out of 10 classes after precision–recall–based threshold calibration.
  - Validation F1 scores reached up to **0.984**.

## Usage

1. **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

2. **Prepare Data**
    - Ensure your dataset is organized and available in the expected directory structure.
    - Update dataset paths in the configuration or script as needed.

3. **Training**
    ```bash
    python train.py
    ```

    - The script handles data preprocessing, augmentation, model training, and validation.
    - Early stopping and learning rate scheduling are incorporated automatically.

4. **Evaluation**
    - The trained model can be evaluated on test data using:
    ```bash
    python eval.py
    ```

    - Precision–recall–based threshold calibration is used for optimal F1 and mAP.

## Results

| Metric      | Value   |
|-------------|---------|
| macro mAP   | 0.9604  |
| Best val F1 | 0.984   |
| ≥0.90 F1    | 8/10 classes |

## References

- Advanced Residual Networks for Multi-label Classification
- Adam Optimizer, ReduceLROnPlateau, Early Stopping

## Authors

- [ChiCoTheLaAnh](https://github.com/ChiCoTheLaAnh)
