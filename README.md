# Data Extraction from P&ID

This project focuses on automated detection and extraction of symbols from Process and Instrumentation Diagrams (P&IDs) using deep learning techniques.

## Overview

P&IDs are complex technical diagrams used in process engineering to show the piping and instrumentation of physical processes. This project uses the YOLOv8 object detection model to automatically identify and classify symbols within these diagrams, streamlining the data extraction process.

## Features

- Detection and classification of symbols in P&ID diagrams
- Implementation using the state-of-the-art YOLOv8 model
- Comprehensive performance evaluation using mAP50, mAP50-95, precision, and recall metrics

## Model Details

The current implementation uses:
- **Model**: YOLOv8
- **Training Configuration**:
  - Epochs: 3
  - Learning Rate: 0.001
  - Batch Size: 4

## Recommended Configuration

For optimal results with complex diagrams, the following parameters are recommended:
- **Epochs**: 100
- **Learning Rate**: 0.0001
- **Batch Size**: 32

## Installation

```bash
# Clone the repository
git clone https://github.com/visheshnayak1/Data-Extraction-from-P-ID.git
cd Data-Extraction-from-P-ID

# Install dependencies
pip install -r requirements.txt
```

## Usage

```python
# Example code for using the trained model
from ultralytics import YOLO

# Load the trained model
model = YOLO('path_to_trained_model.pt')

# Perform detection on a P&ID image
results = model('path_to_pid_image.jpg')

# Process results
for result in results:
    boxes = result.boxes
    # Process detected boxes
```

## Performance Metrics

The model's performance is evaluated using:
- **mAP50**: Mean Average Precision at IoU threshold of 0.5
- **mAP50-95**: Mean Average Precision across IoU thresholds from 0.5 to 0.95
- **Precision**: Ratio of correctly predicted positive observations to total predicted positives
- **Recall**: Ratio of correctly predicted positive observations to all observations in actual class

## Dataset

The model has been trained on a custom dataset of P&ID diagrams with annotated symbols. The dataset includes various symbols commonly found in process engineering diagrams.


## Output for work
![detectecd image](https://github.com/user-attachments/assets/ccfc79bc-77e5-4596-9182-1223977e1a46)


## Future Work

- Increase training epochs to 100 as recommended for improved accuracy
- Implement post-processing to extract structured information from detected symbols
- Expand the dataset to include more symbol variations

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.


Project Link: [https://github.com/visheshnayak1/Data-Extraction-from-P-ID](https://github.com/visheshnayak1/Data-Extraction-from-P-ID)
