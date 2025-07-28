Object Detection of Coins using RF-DETR
This project demonstrates a complete workflow for training and evaluating an RF-DETR object detection model. The goal is to detect different types of coins ("Penny" and "Quarter") from images. The notebook covers everything from model setup and training to detailed performance analysis and visual inspection of the results.

Requirements
The project relies on the following key Python libraries:

rfdetr

pandas

numpy

matplotlib

supervision

Pillow


Usage
To replicate the project, simply run the cells of the Jupyter Notebook (CO2-2_Boquerin.ipynb) in sequential order. The notebook is self-contained and will handle training, analysis, and visualization.

Workflow Overview
The notebook is structured into four main parts:

1. Model Setup and Training
Initialization: An RFDETRBase model is created.

Callback: A custom callback is set up to log the performance metrics (loss, mAP, etc.) at the end of each training epoch.

Training: The model is trained on the Cash Counter dataset for up to 50 epochs, with early stopping enabled to prevent overfitting.

2. Quantitative Performance Analysis
Data Processing: The logged training history is converted into a pandas DataFrame. Key metrics like Accuracy (mAP), Precision (mAP@.50), Recall (AR), and an estimated F1-Score are extracted and calculated.

Metrics Table: A summary table of these final metrics is printed for a quick quantitative overview.

3. Performance Visualization
Loss Curves: The script plots the Training Loss vs. Validation Loss to diagnose the model's learning progress and check for overfitting.

Accuracy Plots: A second plot visualizes how Accuracy, Precision, Recall, and the F1-Score evolve over the epochs.

4. Qualitative Inference and Visualization
Inference: The trained model is used to make predictions on a single sample image from the test set.

Comparison: Using the supervision library, the script generates a side-by-side image that visually compares the model's detections against the original ground-truth annotations. This provides a clear, qualitative assessment of the model's real-world performance.