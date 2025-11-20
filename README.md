# 🐘 Elephant Detection System using YOLOv8

A real-time **elephant detection system** built using **YOLOv8**, capable of processing videos and sending **instant WhatsApp alerts** when elephants are detected.
This project is designed for **wildlife monitoring**, **human–elephant conflict prevention**, and **forest surveillance**.

---

## 🚀 Features

* 🎥 **Real-time Elephant Detection** using YOLOv8 (Ultralytics)
* 📦 Works with any input video (uploaded via notebook)
* ⚡ Optimized inference with frame skipping
* 📩 **Automated WhatsApp Alerts** using Twilio API
* 💾 Saves the processed output video with bounding boxes
* 🧩 Fully reproducible environment setup (pip-based)

---

## 🛠️ Technologies Used

* **Python**
* **YOLOv8 (Ultralytics)**
* **PyTorch**
* **OpenCV**
* **Twilio API (WhatsApp Notifications)**
* **Google Colab (optional)**

---

## 📁 Project Workflow

### 1️⃣ Environment Setup

The notebook removes conflicting libraries and installs a clean stack:

* numpy==1.26.4
* torch==2.5.1
* torchvision==0.20.1
* ultralytics==8.0.172
* opencv-python-headless

### 2️⃣ Upload Video

The user uploads any `.mp4` / `.mov` wildlife surveillance video.

### 3️⃣ Run YOLOv8 Detection

* Loads **yolov8n.pt** (smallest YOLO model for speed)
* Detects elephants in frames
* Draws bounding boxes
* Skips frames for faster performance (FRAME_SKIP = 5)

### 4️⃣ Save Output

The processed video is saved as:

```
elephant_output.mp4
```

### 5️⃣ Send WhatsApp Alerts

When elephants are detected, a message is sent via Twilio:

```
"Alert: Elephant detected in the surveillance area!"
```

---

## 📦 Project Structure (Notebook-Based)

```
Elephant_detection.ipynb
└── Setup environment
└── Upload input video
└── Load YOLO model
└── Run detection
└── Export output video
└── Twilio WhatsApp alert integration
```

---

## 📤 Example Usage (Pseudocode)

```python
model = YOLO("yolov8n.pt")
results = model("input_video.mp4")
```

Send WhatsApp alert:

```python
client.messages.create(
    body="Elephant detected!",
    from_="whatsapp:+14155238886",
    to="whatsapp:+91XXXXXXXXXX"
)
```

---

## 📬 Requirements

* Python 3.10+
* GPU recommended (Colab works well)
* Twilio WhatsApp Sandbox credentials
* YOLOv8 model file

---

## 🔮 Future Enhancements

* Real-time camera stream detection
* Multi-animal detection (tigers, leopards, etc.)
* Geo-tagging alerts
* Dashboard for monitoring
* Integration with drones & edge devices (Jetson Nano, Raspberry Pi)

---

## 📝 Author

**Sanjay Kumar**
GitHub: [https://github.com/Sanjay6113](https://github.com/Sanjay6113)
