# Bangladeshi Sign Language Detection

A deep learning-based system for recognizing static Bangladeshi Sign Language gestures and translating them into text using YOLOv10.

## Project Overview

Communication barriers can make everyday interaction difficult for people with hearing and speech impairments. This project aims to support inclusive communication by detecting and recognizing Bangladeshi Sign Language gestures through computer vision and deep learning.

The system uses a custom dataset of **1,949 labeled images** representing **14 unique static Bangladeshi Sign Language gestures**. A YOLOv10-based object detection model is trained to identify the signs and translate the detected gestures into readable text.

## Key Features

- Detects static Bangladeshi Sign Language gestures.
- Supports 14 different sign classes.
- Uses YOLOv10 for real-time object detection.
- Trained on a custom dataset containing 1,949 labeled images.
- Converts detected gestures into text.
- Provides high precision, recall, and overall recognition accuracy.
- Can be extended for real-time communication applications.

## Technologies Used

- Python
- YOLOv10
- PyTorch
- Computer Vision
- Deep Learning
- Object Detection
- Image Processing
- Custom Dataset
- Google Colab or Jupyter Notebook

## Dataset

The custom dataset contains:

- **Total Images:** 1,949
- **Number of Classes:** 14
- **Task:** Static Bangladeshi Sign Language Gesture Detection
- **Annotation Type:** Object detection bounding boxes

The dataset was prepared and labeled to train the YOLOv10 model for recognizing different Bangladeshi Sign Language gestures.

## Methodology

The overall methodology consists of the following steps:

1. Collect Bangladeshi Sign Language gesture images.
2. Annotate the images using bounding boxes.
3. Prepare and organize the custom dataset.
4. Split the dataset into training, validation, and testing sets.
5. Train the YOLOv10 object detection model.
6. Evaluate the trained model using different performance metrics.
7. Detect sign language gestures from input images or video.
8. Translate the detected signs into text.

## System Workflow

```text
Input Image or Video
        |
        v
Image Preprocessing
        |
        v
YOLOv10-Based Detection Model
        |
        v
Sign Language Gesture Recognition
        |
        v
Detected Sign Class
        |
        v
Text Translation
```

## Model Performance

The trained model achieved the following results:

| Evaluation Metric | Performance |
|-------------------|-------------|
| F1-Confidence | 86% |
| Recall-Confidence | 98% |
| Precision-Confidence | 100% |
| Precision-Recall | 90.3% |
| Overall Average Accuracy | 90.67% |

These results demonstrate that the proposed system can effectively recognize static Bangladeshi Sign Language gestures with high precision and recall.

## Project Structure

```text
SIGN_LANGUAGE_DETECTION/
│
├── dataset/
│   ├── images/
│   ├── labels/
│   └── data.yaml
│
├── runs/
│   └── detect/
│
├── notebooks/
│   └── sign_language_detection.ipynb
│
├── models/
│   └── best.pt
│
├── requirements.txt
├── README.md
└── LICENSE
```

> The project structure may vary depending on the training and deployment environment.

## Installation

Clone the repository:

```bash
git clone https://github.com/shakil2022/SIGN_LANGUAGE_DETECTION.git
```

Navigate to the project directory:

```bash
cd SIGN_LANGUAGE_DETECTION
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Required Packages

The project can be executed using the following Python packages:

```text
ultralytics
torch
torchvision
opencv-python
numpy
matplotlib
pandas
pyyaml
```

Install them using:

```bash
pip install ultralytics torch torchvision opencv-python numpy matplotlib pandas pyyaml
```

## Training

To train the YOLOv10 model, configure the dataset path in the dataset configuration file and run the training script or notebook.

Example:

```python
from ultralytics import YOLO

model = YOLO("yolov10n.pt")

model.train(
    data="dataset/data.yaml",
    epochs=100,
    imgsz=640,
    batch=16
)
```

## Inference

After training, the best model weights can be used to detect sign language gestures from an image.

```python
from ultralytics import YOLO

model = YOLO("models/best.pt")

results = model.predict(
    source="test_image.jpg",
    conf=0.25,
    save=True
)
```

For webcam or video-based detection:

```python
from ultralytics import YOLO

model = YOLO("models/best.pt")

results = model.predict(
    source=0,
    show=True,
    conf=0.25
)
```

## Applications

This project can be used in:

- Assistive communication systems.
- Educational platforms for sign language learning.
- Human-computer interaction.
- Smart classroom environments.
- Accessibility-focused applications.
- Real-time sign language translation systems.
- Communication support for people with hearing and speech impairments.

## Future Improvements

Possible future improvements include:

- Increasing the number of recognized sign classes.
- Adding dynamic sign language gesture recognition.
- Developing a real-time mobile application.
- Integrating speech synthesis for text-to-speech conversion.
- Improving performance under different lighting conditions.
- Supporting continuous sign language sentence recognition.
- Deploying the model on edge devices.
- Developing a web-based sign language translation platform.

## Project Highlights

- Developed a YOLOv10-based Bangladeshi Sign Language detection system.
- Created a custom dataset containing 1,949 labeled images.
- Recognized 14 static Bangladeshi Sign Language gestures.
- Achieved an overall average accuracy of 90.67%.
- Designed the system to translate detected gestures into text.
- Focused on improving accessibility and reducing communication barriers.

## GitHub Repository

Repository link:

[Bangladeshi Sign Language Detection](https://github.com/shakil2022/SIGN_LANGUAGE_DETECTION)

## Author

**Md. Shakil Ahmed**

Lecturer  
Department of Computer Science and Engineering  
Bangladesh University of Business and Technology

## License

This project is intended for academic and research purposes. Add an appropriate open-source license if you plan to distribute or reuse the project publicly.
