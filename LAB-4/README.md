# IT549: Deep Learning  
## Lab Assignment 4: Object Detection Evolution  

Name: Kunj Shah  
ID: 202511031  

---

## Overview
This assignment explores the evolution of object detection models from **R-CNN → Fast R-CNN → Faster R-CNN → YOLO**.  
We implement core components and analyze improvements in **speed and accuracy**.

**Dataset:** Fruit Images Dataset (Apple, Banana, Orange)

---

## Tasks

### 🔹 Ground Truth Visualization
- Parsed Pascal VOC XML annotations  
- Drew bounding boxes on images  
- Verified dataset correctness  

---

### 🔹 Task 1: IoU (Intersection over Union)
- Implemented IoU from scratch  
- Measures overlap between predicted and actual boxes  

---

### 🔹 Task 2: Selective Search (R-CNN)
- Generated region proposals (~1000+)  
- Visualized top regions  
- Highlighted inefficiency  

---

### 🔹 Task 3: R-CNN Bottleneck
- Used pre-trained ResNet18  
- Ran CNN on each proposal  
- High computation (redundant processing)  

---

### 🔹 Task 4: Fast R-CNN
- Single CNN pass on full image  
- Used RoI Pooling  
- Reduced computation  

---

### 🔹 Task 5: Faster R-CNN
- Introduced Region Proposal Network (RPN)  
- End-to-end training  
- Faster + more accurate  

---

### 🔹 Task 6: Non-Maximum Suppression (NMS)
- Removed duplicate boxes  
- Controlled using IoU threshold (~0.5)  

---

### 🔹 Task 7: YOLO Fine-Tuning
- Used YOLOv8 (Nano)  
- Trained on fruit dataset  
- Single-shot detection (fastest)  

---

## 📊 Model Comparison

| Model          | Speed        | Key Idea                  |
|---------------|-------------|--------------------------|
| R-CNN         | ❌ Slow      | CNN per region           |
| Fast R-CNN    | ✅ Faster    | Shared feature map       |
| Faster R-CNN  | ✅✅ Fast     | RPN                      |
| YOLO          | ✅✅✅ Fastest | Single-shot detection    |

---

## Key Takeaways
- Reduced redundant computation across models  
- Shift from **region-based → unified detection**  
- YOLO achieves real-time performance  

---

## Tech Stack
- Python, NumPy  
- OpenCV, Matplotlib  
- PyTorch  
- Ultralytics YOLOv8  

---

