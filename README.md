# 🚗 Driver Drowsiness Detection

## 📌 Project Overview
This project implements a **Driver Drowsiness Detection System** using **OpenCV, MediaPipe, and Pygame**. The system detects signs of drowsiness and alerts the driver using an alarm sound.

### 🛠 Features:
- 👀 **Eye Blink Detection** – Detects and analyzes blinking patterns
- 💤 **Sleepiness Detection** – Identifies prolonged eye closure
- 🏁 **Yawning Detection** – Monitors mouth movements
- 🎵 **Alarm System** – Plays an alert sound when drowsiness is detected
- 📈 **Real-time Processing** – Uses **OpenCV** and **MediaPipe** for fast detection

---

## 🖥️ Technologies Used
- **Python** 🐍
- **OpenCV** 👀 (for real-time video processing)
- **MediaPipe** 🏗️ (for facial landmark detection)
- **Scipy** 📊 (for calculating Euclidean distances)
- **Pygame** 🔊 (for playing alarm sounds)
- **NumPy** 🔢 (for array operations)

---

## 📸 How It Works
1️⃣ Captures a real-time video stream from the webcam 📷
2️⃣ Detects facial landmarks using MediaPipe 🤖
3️⃣ Extracts eye and mouth regions 🏁
4️⃣ Calculates blink and yawn ratios using Euclidean distances 📏
5️⃣ Classifies driver state as **Active 😃**, **Drowsy 😴**, or **Sleeping 💤**
6️⃣ Plays an alarm if sleepiness is detected 🚨

---

## 🔍 Setup & Installation
1️⃣ **Clone the Repository**
```bash
git clone https://github.com/your-username/Driver-Drowsiness-Detection.git
cd Driver-Drowsiness-Detection
```

2️⃣ **Install Dependencies**
```bash
pip install opencv-python mediapipe pygame scipy numpy
```

3️⃣ **Run the Application**
```bash
python driver_drowsiness.py
```

---

## 🎯 Key Code Components
### 👀 Eye Blink Detection
```python
def blinked(arr):
    up = distance.euclidean(arr[3], arr[13]) + distance.euclidean(arr[4], arr[12]) + distance.euclidean(arr[5], arr[11])
    down = distance.euclidean(arr[0], arr[8])
    ratio = round((up / (3.0 * down)), 2)
    return 2 if ratio > 0.27 else 1 if ratio > 0.21 else 0
```

### 💤 Yawning Detection
```python
def yawning(arr):
    up = distance.euclidean(arr[2], arr[3]) + distance.euclidean(arr[6], arr[7]) + distance.euclidean(arr[4], arr[5])
    down = distance.euclidean(arr[0], arr[1])
    return 1 if (up / (3.0 * down)) < 0.5 else 0
```

---

## 🚀 Future Enhancements
🔹 Improve accuracy using deep learning (CNN, LSTM)

🔹 Integrate with IoT devices for real-time vehicle alerts

🔹 Add driver distraction detection (e.g., phone use, looking away)

---

## 🏆 Contributions & Feedback
💡 Suggestions and contributions are welcome! Feel free to **fork**, create a **pull request**, or open an **issue**.

---

### ⭐ If you like this project, don't forget to give it a star! ⭐

