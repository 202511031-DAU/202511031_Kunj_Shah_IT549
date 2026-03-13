# IT549: Deep Learning – Lab 3
# Image-Based AQI Classification using CNN and Pretrained Models

**Name:** Shah Kunj
**Student ID:** 202511031
**Course:** IT549 – Deep Learning    

---

## 📌 Project Overview

This project demonstrates the use of deep learning for environmental image classification. The goal is to predict the **Air Quality Index (AQI) Class** from images of locations using two approaches:

1. **Basic CNN** – A Convolutional Neural Network trained from scratch
2. **MobileNetV2** – A pretrained model fine-tuned using Transfer Learning

The project covers a complete deep learning pipeline including data preprocessing, model building, training, evaluation, and misclassification analysis.

---

## 📂 Dataset

- **Source:** [Google Drive Dataset Link](https://drive.google.com/drive/folders/1usBxgNB67GfhCQ2f7xRkDlF6fgIZZrP?usp=sharing)
- **Total Images:** ~6000
- **CSV File:** `data.csv` — contains image filenames and corresponding AQI labels
- **Image Folder:** `sampled_images/` — contains all images

### AQI Classes (6 total)

| Class Label | AQI Range | Description |
|---|---|---|
| a_Good | 0–50 | Air quality is satisfactory |
| b_Satisfactory | 51–100 | Acceptable air quality |
| c_Moderate | 101–200 | Sensitive groups may be affected |
| d_Poor | 201–300 | Unhealthy for general public |
| e_Very_Poor | 301–400 | Health warnings |
| f_Severe | 401–500 | Emergency conditions |

### Fields Used
- `image_path` — input image filename
- `AQI_Class` — target classification label

## Tasks
| Task | Description |
|---|---|
| 1 | Data loading, preprocessing, 70/15/15 split |
| 2 | Custom CNN trained from scratch |
| 3 | MobileNetV2 transfer learning + fine-tuning |
| 4 | Accuracy, Precision, Recall, F1, Confusion Matrix |
| 5 | Training curves + discussion |
| 6 | Misclassification analysis |

## Results
| Model | Accuracy | F1-Score |
|---|---|---|
| Basic CNN | ~0.61 | ~0.60 |
| MobileNetV2 | ~0.82 | ~0.81 |

