# Object-detection



YOLO Object Detection with OpenCV

This project demonstrates how to use a YOLO (You Only Look Once) object detection model with OpenCV to detect objects in an image. The primary focus of this project is accident detection, but it can be adapted to various object detection tasks.

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Customization](#customization)
- [Acknowledgements](#acknowledgements)

## Features

- Load and use a YOLO model to detect objects in an image.
- Configure detection confidence thresholds.
- Parse detection results (class IDs, confidence scores, bounding boxes).
- Display results with a detection-based message (e.g., accident detection).

## Requirements

- Python 3.6+
- Required libraries:
  - OpenCV
  - NumPy
  - Torch

Install the required libraries using pip:
```bash
pip install opencv-python numpy torch
```

## Installation

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_folder>
   ```

2. Ensure the YOLO model weights are available. Place the `.pt` file in an accessible directory and update the `model_path` variable in the script.

3. Download or prepare an input image for testing.

## Usage

1. Place your YOLO model weights in the specified path (e.g., `best.pt`).
2. Load the image for testing (update `output_image` path in the script).
3. Run the script:
4. The script will output whether an accident is detected or not based on the number of detected objects.

## How It Works

1. **Model Loading:**
   The YOLO model is loaded using OpenCV's `cv2.dnn.readNet`.

2. **Image Preprocessing:**
   The input image is resized to the required dimensions (416x416), normalized, and converted into a blob.

3. **Object Detection:**
   The network performs a forward pass to output bounding boxes, class IDs, and confidence scores.

4. **Result Filtering:**
   Detections with confidence scores above the threshold (`conf_thres=0.4` by default) are retained and parsed.

5. **Accident Detection Logic:**
   The number of detected objects is checked. If any objects are detected, the script concludes that an accident has occurred.

## Customization

- **Confidence Threshold:**
  Modify the `conf_thres` parameter to adjust detection sensitivity.

- **Model Path:**
  Update the `model_path` variable with the path to your YOLO model.

- **Detection Logic:**
  Adapt the `message` logic to suit your application requirements.

## Acknowledgements

- [YOLO](https://pjreddie.com/darknet/yolo/) for real-time object detection.
- [OpenCV](https://opencv.org/) for providing efficient computer vision tools.
- [PyTorch](https://pytorch.org/) for enabling deep learning support.
