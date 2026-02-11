
# 🔥 Fire & Smoke Detection using YOLOv8

Real-time Fire and Smoke Detection using YOLOv8 trained on a custom dataset and exported for deployment using ONNX.

---

## 📌 Project Overview

This project implements an object detection system capable of detecting:

* 🔥 Fire
* 🌫 Smoke

The model is trained using **Ultralytics YOLOv8** and evaluated on a validation dataset with strong precision and recall performance. The trained model is exported to ONNX for deployment compatibility and production inference pipelines.

---

## 🎯 Problem Statement

Early detection of fire and smoke is critical for:

* Industrial safety systems
* Forest fire monitoring
* Surveillance systems
* Smart city infrastructure

This project demonstrates how deep learning can be leveraged to automate fire hazard detection efficiently and reliably.

---

## 🛠 Tech Stack

| Component     | Technology   |
| ------------- | ------------ |
| Model         | YOLOv8       |
| Framework     | PyTorch      |
| Export Format | ONNX         |
| Environment   | Google Colab |
| Language      | Python       |

---

## 📂 Project Structure

```
Fire and Smoke Detection/
│
├── data.yaml
├── best.pt
├── best.onnx
├── runs/
│   └── detect/
│       ├── val/
│       └── predict3/
├── README.md
└── requirements.txt
```

---

## 🚀 Installation

Clone the repository:

```bash
git clone https://github.com/nitikachauhann/Fire-and-Smoke-Detection.git
cd Fire-and-Smoke-Detection
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Or install Ultralytics directly:

```bash
pip install ultralytics
```

---

## 🏋️ Model Training

```bash
yolo task=detect mode=train model=yolov8n.pt data=data.yaml epochs=50 imgsz=640
```

---

## 📊 Model Evaluation

```bash
yolo task=detect mode=val model=best.pt data=data.yaml
```

### Validation Results

| Metric    | Value |
| --------- | ----- |
| Precision | 0.941 |
| Recall    | 0.891 |
| mAP@50    | 0.896 |
| mAP@50-95 | 0.491 |

### Per-Class Performance

| Class | Precision | Recall |
| ----- | --------- | ------ |
| Fire  | 0.915     | 0.833  |
| Smoke | 0.966     | 0.949  |

---

## 📦 Export to ONNX

```bash
yolo export model=best.pt format=onnx
```

The exported model can be used in:

* ONNX Runtime
* Edge devices
* Production inference systems

---

## 🖼 Sample Predictions

After running inference, YOLOv8 automatically saves output results inside:

```
Fire and Smoke Detection/runs/detect/predict3/
```

This folder contains:

* Annotated images with bounding boxes
* Class labels (Fire / Smoke)
* Confidence scores

To run prediction manually:

```bash
yolo task=detect mode=predict model=best.pt source=path_to_image_or_video
```

Each new prediction run creates a new folder:

```
runs/detect/predictX/
```

## 📈 Performance Summary

* High overall precision (94.1%)
* Strong smoke detection performance
* Lightweight YOLOv8 model suitable for real-time inference
* ONNX export enables deployment flexibility

---

## 🔮 Future Improvements

* Real-time webcam detection
* Edge device deployment (Jetson / Raspberry Pi)
* Alarm integration system
* Cloud-based monitoring dashboard
* Model optimization using TensorRT or OpenVINO



