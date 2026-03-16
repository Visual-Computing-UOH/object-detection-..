# 🎯 Real-Time Object Detection System

A real-time object detection application powered by **YOLOv8** and **OpenCV** that detects 80 everyday objects through your webcam — with a live on-screen counter panel.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)
![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-purple?style=flat-square)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green?style=flat-square&logo=opencv)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

---

## 📸 Features

- ✅ Real-time detection via webcam at 720p
- ✅ Detects **80 object classes** (people, phones, laptops, cars, animals, furniture & more)
- ✅ Live **object count panel** — shows each detected class and total count
- ✅ Color-coded bounding boxes with confidence scores
- ✅ FPS counter overlay
- ✅ Works in **VS Code** and **Jupyter Notebook**

---

## 🧠 Detectable Objects (80 COCO Classes)

| Category | Objects |
|----------|---------|
| 👤 People | person |
| 🚗 Vehicles | bicycle, car, motorcycle, airplane, bus, train, truck, boat |
| 🚦 Street | traffic light, fire hydrant, stop sign, parking meter, bench |
| 🐾 Animals | bird, cat, dog, horse, sheep, cow, elephant, bear, zebra, giraffe |
| 👜 Accessories | backpack, umbrella, handbag, tie, suitcase |
| 🏅 Sports | frisbee, skis, snowboard, sports ball, kite, baseball bat, skateboard, surfboard, tennis racket |
| 🍽️ Kitchen | bottle, wine glass, cup, fork, knife, spoon, bowl |
| 🍎 Food | banana, apple, sandwich, orange, broccoli, carrot, hot dog, pizza, donut, cake |
| 🪑 Furniture | chair, couch, potted plant, bed, dining table, toilet |
| 💻 Electronics | tv, laptop, mouse, remote, keyboard, cell phone, microwave, oven, toaster, sink, refrigerator |
| 📚 Misc | book, clock, vase, scissors, teddy bear, hair drier, toothbrush |

---

## 📁 Project Structure

```
📦 object-detection
 ┣ 📄 detect.py                  ← Run in VS Code / terminal
 ┣ 📓 object_detection.ipynb     ← Run in Jupyter Notebook
 ┗ 📄 README.md
```

---

## ⚙️ Requirements

- Python 3.8 or higher
- Webcam connected to your PC

---

## 🚀 Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/object-detection.git
cd object-detection
```

### 2. Install dependencies

```bash
pip install opencv-python ultralytics
```

> The YOLOv8 model weights (`yolov8s.pt`) will **auto-download** on first run (~22 MB).

---

## ▶️ How to Run

### Option A — VS Code / Terminal

```bash
python detect.py
```

A window will open showing your webcam feed with detection overlays.  
**Press `Q`** to quit.

### Option B — Jupyter Notebook

```bash
jupyter notebook
```

Open `object_detection.ipynb` and run each cell from top to bottom.  
The camera window opens on the last cell. **Press `Q`** to stop.

---

## 🖥️ What You'll See on Screen

| Element | Description |
|---------|-------------|
| **Colored boxes** | Drawn around each detected object |
| **Label tag** | Shows object name + confidence % (e.g. `person 94%`) |
| **Count panel** | Top-left overlay listing all detected classes and counts |
| **TOTAL** | Grand total of all objects currently in frame |
| **FPS** | Frames per second shown top-right |

---

## 🔧 Configuration

Inside `detect.py` you can tweak these settings:

```python
# Change model size for speed vs accuracy tradeoff:
model = YOLO("yolov8n.pt")   # nano   — fastest, least accurate
model = YOLO("yolov8s.pt")   # small  — balanced (default)
model = YOLO("yolov8m.pt")   # medium — slower, more accurate
model = YOLO("yolov8l.pt")   # large  — best accuracy

# Change detection confidence threshold (0.0 to 1.0):
results = model(frame, stream=True, conf=0.35)
# Lower = detects more (may include false positives)
# Higher = stricter detections only
```

---

## 🛠️ Tech Stack

| Library | Purpose |
|---------|---------|
| [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) | AI object detection model |
| [OpenCV](https://opencv.org/) | Webcam capture & drawing overlays |
| Python `collections.Counter` | Per-frame object counting |

---

## 📌 Notes

- Detection is limited to the **80 COCO dataset classes** listed above
- For detecting custom objects (e.g. specific products, tools), a custom-trained YOLOv8 model would be needed
- Performance depends on your CPU/GPU — a dedicated GPU will run at much higher FPS

---

## 📄 License

This project is open source under the [MIT License](LICENSE).

---

## 🙌 Acknowledgements

- [Ultralytics](https://ultralytics.com/) for YOLOv8
- [COCO Dataset](https://cocodataset.org/) for the pre-trained weights
