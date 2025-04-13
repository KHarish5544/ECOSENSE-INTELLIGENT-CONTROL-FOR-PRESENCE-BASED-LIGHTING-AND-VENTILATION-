
ECOSENSE: Intelligent Control for Presence-Based Lighting and Ventilation

A smart automation system leveraging YOLOv8 for **real-time human presence detection**, **fan and light control**, and **fire alert**, using just a camera — no additional sensors required!

---

Project Overview

ECOSENSE uses computer vision and AI to detect people, fans, and ambient light levels using a webcam. Based on these detections, it intelligently controls:
- 💡 Lights (on/off based on brightness),
- 🌀 Fans (on/off based on human position),
- 🔥 Alarm (on when no human presence for safety alert or fire integration).

---

Technologies Used

- Python
- OpenCV
- YOLOv8 (via Ultralytics)
- cvzone
- NumPy
- Real-time webcam processing

---

📂 File Structure

```
├── main_fan_light.py       # Core script for smart detection and control
├── /Yolo_weights/          # Folder containing YOLOv8 weights
│   ├── yolov8n.pt          # For person detection
│   └── Fan.pt              # For fan detection
├── README.md               # This file
```

---

How It Works

🔹 Fan Automation

- Detects human and fan using two separate YOLOv8 models.
- Checks if the person is **directly under the fan**.
- Turns **Fan ON** if both detections are confident and spatially aligned.

---

🔹 Light Automation

- Converts the frame to grayscale and calculates **average intensity**.
- If brightness is below a certain threshold (e.g., 75), it turns the **light ON**.

---

🔹 Alarm Trigger

- If **no human is detected** for more than 10 seconds, an alarm is raised (textual simulation).
- Can be extended to trigger actual alarms for fire/safety.

---

How to Run

Prerequisites

Install the dependencies:

```bash
pip install opencv-python cvzone ultralytics numpy
```

Run the Script

```bash
python main_fan_light.py
```

Press `q` to quit the camera feed.

---

⚙️ Configuration Options

| Parameter              | Description                                      | Default |
|------------------------|--------------------------------------------------|---------|
| `light_threshold`      | Threshold for brightness (for Light ON/OFF)     | 75      |
| `confidence_threshold` | YOLO detection confidence level                 | 0.7     |
| `fan_debounce_time`    | Time before toggling fan state again (seconds)  | 5       |
| `alarm_trigger_time`   | Time without person before triggering alarm     | 10      |


---

🛠 Future Improvements

- Integrate fire detection YOLO model
- Add GPIO control for Raspberry Pi integration
- Remote control via mobile app
- Voice assistant support

---

🏅 Project Recognition

- Presented at Dr. A.P.J. Abdul Kalam Awards
- Developed by:
  - Harish K
  - Bhuvanraj R
  - Karishma S K  
*(M. Kumarasamy College of Engineering)*

---

📜 License

This project is licensed under the [MIT License](LICENSE).

---

Would you like me to generate the GitHub repository structure for this or export the `README.md` file?
