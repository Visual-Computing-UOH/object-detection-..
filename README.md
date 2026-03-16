🎯 Real-Time Object Detection System
A real-time object detection application powered by YOLOv8 and OpenCV that detects 80 everyday objects through your webcam — with a live on-screen counter panel. 

📸 Features

✅ Real-time detection via webcam at 720p
✅ Detects 80 object classes (people, phones, laptops, cars, animals, furniture & more)
✅ Live object count panel — shows each detected class and total count
✅ Color-coded bounding boxes with confidence scores
✅ FPS counter overlay
✅ Works in VS Code and Jupyter Notebook


🧠 Detectable Objects (80 COCO Classes)
CategoryObjects👤 Peopleperson🚗 Vehiclesbicycle, car, motorcycle, airplane, bus, train, truck, boat🚦 Streettraffic light, fire hydrant, stop sign, parking meter, bench🐾 Animalsbird, cat, dog, horse, sheep, cow, elephant, bear, zebra, giraffe👜 Accessoriesbackpack, umbrella, handbag, tie, suitcase🏅 Sportsfrisbee, skis, snowboard, sports ball, kite, baseball bat, skateboard, surfboard, tennis racket🍽️ Kitchenbottle, wine glass, cup, fork, knife, spoon, bowl🍎 Foodbanana, apple, sandwich, orange, broccoli, carrot, hot dog, pizza, donut, cake🪑 Furniturechair, couch, potted plant, bed, dining table, toilet💻 Electronicstv, laptop, mouse, remote, keyboard, cell phone, microwave, oven, toaster, sink, refrigerator📚 Miscbook, clock, vase, scissors, teddy bear, hair drier, toothbrush

📁 Project Structure
📦 object-detection
 ┣ 📄 detect.py                  ← Run in VS Code / terminal
 ┣ 📓 object_detection.ipynb     ← Run in Jupyter Notebook
 ┗ 📄 README.md

⚙️ Requirements

Python 3.8 or higher
Webcam connected to your PC


🚀 Installation & Setup
1. Clone the repository
bashgit clone https://github.com/YOUR_USERNAME/object-detection.git
cd object-detection
2. Install dependencies
bashpip install opencv-python ultralytics

The YOLOv8 model weights (yolov8s.pt) will auto-download on first run (~22 MB).


▶️ How to Run
Option A — VS Code / Terminal
bashpython detect.py
A window will open showing your webcam feed with detection overlays.
Press Q to quit.
Option B — Jupyter Notebook
bashjupyter notebook
Open object_detection.ipynb and run each cell from top to bottom.
The camera window opens on the last cell. Press Q to stop.

🖥️ What You'll See on Screen
ElementDescriptionColored boxesDrawn around each detected objectLabel tagShows object name + confidence % (e.g. person 94%)Count panelTop-left overlay listing all detected classes and countsTOTALGrand total of all objects currently in frameFPSFrames per second shown top-right

🔧 Configuration
Inside detect.py you can tweak these settings:
python# Change model size for speed vs accuracy tradeoff:
model = YOLO("yolov8n.pt")   # nano   — fastest, least accurate
model = YOLO("yolov8s.pt")   # small  — balanced (default)
model = YOLO("yolov8m.pt")   # medium — slower, more accurate
model = YOLO("yolov8l.pt")   # large  — best accuracy

# Change detection confidence threshold (0.0 to 1.0):
results = model(frame, stream=True, conf=0.35)
# Lower = detects more (may include false positives)
# Higher = stricter detections only

🛠️ Tech Stack
LibraryPurposeUltralytics YOLOv8AI object detection modelOpenCVWebcam capture & drawing overlaysPython collections.CounterPer-frame object counting

📌 Notes

Detection is limited to the 80 COCO dataset classes listed above
For detecting custom objects (e.g. specific products, tools), a custom-trained YOLOv8 model would be needed
Performance depends on your CPU/GPU — a dedicated GPU will run at much higher FPS


📄 License
This project is open source under the MIT License.

🙌 Acknowledgements

Ultralytics for YOLOv8
COCO Dataset for the pre-trained weights
