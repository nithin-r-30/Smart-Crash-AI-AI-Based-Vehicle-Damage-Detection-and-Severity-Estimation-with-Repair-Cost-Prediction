# 🚗 Smart Crash AI – AI-Based Vehicle Damage Detection and Severity Estimation with Repair Cost Prediction

## 📌 Project Overview

**Smart Crash AI** is an AI-powered vehicle damage assessment system developed using Deep Learning, Computer Vision, and YOLOv8.

The system automatically detects and classifies vehicle damages from uploaded images, estimates the severity of the detected damage, and predicts the approximate repair cost.

It provides a Streamlit-based web application where users can upload vehicle images, visualize detected damage regions, view severity levels, and generate detailed vehicle damage assessment reports.

The main objective is to automate traditional vehicle damage inspection, reduce manual effort, minimize human errors, and support faster vehicle insurance and repair assessment.

## 🎯 Objectives

- Develop an AI-based system for automatic vehicle damage detection.
- Identify and classify different types of vehicle damage.
- Estimate damage severity as Minor, Moderate, or Severe.
- Predict approximate vehicle repair costs.
- Develop an interactive Streamlit web application.
- Generate structured vehicle damage assessment reports.

## ✨ Key Features

- **Automated Damage Detection:** Detects vehicle damage using YOLOv8.
- **Damage Classification:** Identifies eight categories of vehicle damage.
- **Severity Estimation:** Classifies damage into Minor, Moderate, and Severe.
- **Repair Cost Prediction:** Estimates repair expenses using a rule-based cost estimation model.
- **Image Upload:** Allows users to upload vehicle images.
- **Visual Detection:** Displays detected damage regions with bounding boxes.
- **No-Damage Detection:** Identifies images without visible vehicle damage.
- **Report Generation:** Generates detailed damage assessment reports.
- **Interactive Interface:** Provides a user-friendly Streamlit web application.

## 🛠️ Technologies Used

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Deep Learning | YOLOv8 |
| Computer Vision | OpenCV |
| Deep Learning Framework | PyTorch |
| Web Framework | Streamlit |
| Data Processing | NumPy, Pandas |
| Data Visualization | Matplotlib |
| Configuration | YAML |
| Development Environment | VS Code |

## 📂 Dataset Information

The project uses three publicly available vehicle damage datasets:

1. **VehiDE Dataset**
   - Vehicle damage images.
   - Bounding box annotations.
   - Multiple damage categories.

2. **TQVCD Dataset**
   - Vehicle condition images.
   - Front and rear vehicle views.

3. **CarDD Dataset**
   - Diverse vehicle damage images.
   - COCO-format annotations.
   - Multiple damage categories.

### Dataset Preprocessing

- Image cleaning and validation.
- Duplicate and corrupted image removal.
- Annotation conversion.
- Damage class mapping.
- Image resizing and normalization.
- Dataset splitting.

**Dataset Split:**
- Training: 70%
- Validation: 15%
- Testing: 15%

*Note: The original datasets are not included in this repository.*

## 🔍 Damage Categories

| Class ID | Damage Type |
|---|---|
| 0 | Scratch |
| 1 | Dent |
| 2 | Crack |
| 3 | Broken Part |
| 4 | Glass Damage |
| 5 | Paint Damage |
| 6 | Corrosion |
| 7 | Crushed Deformation |

## 📊 Severity Estimation

The system estimates severity based on damage type, bounding box size, relative damage area, and detection confidence.

| Severity | Damage Area |
|---|---|
| Minor | Less than 5% |
| Moderate | 5%–15% |
| Severe | Greater than 15% |

## 💰 Repair Cost Prediction

The system uses a rule-based approach to estimate repair costs based on the detected damage category and severity level.

**Formula:**

Repair Cost = Base Cost × Severity Multiplier

### Base Repair Cost

| Damage Type | Base Cost |
|---|---:|
| Scratch | ₹1,500 |
| Dent | ₹5,000 |
| Crack | ₹3,000 |
| Broken Part | ₹15,000 |
| Glass Damage | ₹8,000 |
| Paint Damage | ₹2,500 |
| Corrosion | ₹4,000 |
| Crushed Deformation | ₹20,000 |

*Note: These are approximate project-defined estimates and not official repair quotations.*

## ⚙️ Model Training Configuration

The project uses transfer learning with the YOLOv8n pretrained model.

| Parameter | Configuration |
|---|---|
| Model | YOLOv8n |
| Epochs | 40 |
| Batch Size | 16 |
| Image Size | 512 × 512 |
| Optimizer | SGD |
| Learning Rate | 0.01 |
| Patience | 12 |

The trained model weights are saved as `best.pt`.

## 📈 Model Evaluation

| Evaluation Metric | Reported Value |
|---|---:|
| Precision | 0.782 |
| Recall | 0.469 |
| F1 Score | 0.553 |
| mAP@50 | 0.369 |
| mAP@50-95 | 0.279 |

The evaluation includes:
- Precision and Recall curves.
- F1 Score analysis.
- Precision-Recall curve.
- Confusion Matrix.
- Validation performance analysis.

*Note: These values are reported in the project report and should be verified against the final training evaluation.*

## 🏗️ System Workflow

1. Collect vehicle damage datasets.
2. Preprocess and annotate images.
3. Train the YOLOv8 model.
4. Upload a vehicle image through the Streamlit application.
5. Detect and classify damaged regions.
6. Estimate the damage severity.
7. Calculate the approximate repair cost.
8. Generate the vehicle damage assessment report.

## 💻 Installation and Execution

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/smart-crash-ai.git
```

### 2. Navigate to the Project Directory

```bash
cd smart-crash-ai
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate on Windows:

```bash
venv\Scripts\activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Add the Trained Model

Place the trained model inside the appropriate directory.

```text
models/best.pt
```

### 6. Run the Application

```bash
streamlit run app.py
```

### 7. Open the Application

```text
http://localhost:8501
```

## 📁 Project Structure

```text
Smart-Crash-AI/
│
├── app.py
├── train.py
├── preprocess.py
├── evaluate_full.py
│
├── src/
│   ├── detector.py
│   ├── severity_estimator.py
│   ├── cost_estimator.py
│   └── utilities.py
│
├── models/
│   └── best.pt
│
├── dataset/
│   ├── images/
│   ├── labels/
│   └── data.yaml
│
├── outputs/
├── reports/
│
├── config.yaml
├── requirements.txt
└── README.md
```

*Adjust the structure according to the actual files in the repository.*

## 🌍 Applications

- Vehicle insurance claim assessment.
- Automobile repair centers.
- Vehicle inspection agencies.
- Fleet management organizations.
- Vehicle maintenance and damage analysis.
- Automotive research and development.

## ⚠️ Limitations

- Detection accuracy depends on image quality.
- Internal mechanical damage cannot be detected.
- Very small scratches and minor damages may be difficult to identify.
- Repair costs are approximate.
- The system supports predefined damage categories.
- The current version focuses on static image analysis rather than continuous live video processing.

## 🚀 Future Enhancements

- Develop a mobile application.
- Implement real-time vehicle damage detection.
- Improve AI-based repair cost prediction.
- Integrate with insurance claim management systems.
- Extend support to bikes, trucks, buses, and other vehicles.
- Improve detection performance using larger and more diverse datasets.

## 🏫 Institution

**Mysore University School of Engineering (MUSE)**  
University of Mysore  
Manasagangotri Campus, Mysuru.

**Academic Year:** 2025–2026

## 📜 Conclusion

Smart Crash AI demonstrates the application of Artificial Intelligence, Deep Learning, and Computer Vision in automating vehicle damage assessment.

By integrating YOLOv8-based damage detection, severity estimation, and repair cost prediction into a single Streamlit web application, the project provides a convenient approach to vehicle damage analysis.

The system aims to reduce manual inspection effort, improve assessment consistency, and support efficient vehicle repair and insurance claim processing.

---

⭐ If you find this project interesting, consider giving this repository a star!

**Project:** Smart Crash AI  
**Domain:** Artificial Intelligence | Deep Learning | Computer Vision | Automotive Technology
