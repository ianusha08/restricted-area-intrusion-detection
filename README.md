# 🔐 Area-Restricted Intrusion Detection System

> A real-time AI-powered security system that monitors a restricted area through a live webcam feed and triggers alerts when an unauthorized person is detected inside the zone.

![Python](https://img.shields.io/badge/Python-3.10-blue?style=flat-square&logo=python)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green?style=flat-square&logo=opencv)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0.10-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)

---

## 📌 Overview

Traditional security systems rely on manual monitoring, which is inefficient and prone to human error. This project replaces manual surveillance with an **automated, intelligent intrusion detection system** that:

- Continuously monitors a live camera feed
- Uses **AI-based human pose detection** (not simple motion detection)
- Defines a **restricted polygon zone** on the frame
- Fires an alert only when a person stays inside the zone for a set duration
- Sends an **SMS notification** via Twilio and logs all events

This was developed as a **Minor Project** for the B.Tech Computer Science program.

---

## 🎯 Features

| Feature | Details |
|---|---|
| 👁️ Live Monitoring | Real-time webcam feed processed frame by frame |
| 🤖 AI Pose Detection | MediaPipe detects 33 human body landmarks |
| 📐 Restricted Zone | Customizable polygon zone drawn on the video |
| 🎨 Visual Feedback | Zone turns red when intruder detected |
| ⏱️ Time-Based Alert | Alert fires only after 3 continuous seconds in zone |
| 📱 SMS Alert | Twilio sends instant SMS to configured number |
| 🔕 Cooldown System | 15-second cooldown prevents repeated alert spam |
| 📋 Event Logging | Every entry, exit, and alert logged to console |
| ❌ False Alarm Filter | Passing-by persons do not trigger alerts |

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Python 3.10** | Core programming language |
| **OpenCV** | Video capture, frame processing, UI rendering |
| **cvzone 1.6.1** | Simplified MediaPipe Pose wrapper |
| **MediaPipe** | AI/ML pose estimation (33 body landmarks) |
| **NumPy** | Polygon zone definition and math |
| **Twilio** | Cloud SMS alert delivery |

---

## 🧠 How It Works
\#chatgpt-mermaid-\_r_ur\_{font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";font-size:16px;fill:rgb(237, 237, 237);}@keyframes edge-animation-frame{from{stroke-dashoffset:0;}}@keyframes dash{to{stroke-dashoffset:0;}}#chatgpt-mermaid-\_r_ur\_ .edge-animation-slow{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 50s linear infinite;stroke-linecap:round;}#chatgpt-mermaid-\_r_ur\_ .edge-animation-fast{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 20s linear infinite;stroke-linecap:round;}#chatgpt-mermaid-\_r_ur\_ .error-icon{fill:rgb(48, 48, 48);}#chatgpt-mermaid-\_r_ur\_ .error-text{fill:rgb(237, 237, 237);stroke:rgb(237, 237, 237);}#chatgpt-mermaid-\_r_ur\_ .edge-thickness-normal{stroke-width:1px;}#chatgpt-mermaid-\_r_ur\_ .edge-thickness-thick{stroke-width:3.5px;}#chatgpt-mermaid-\_r_ur\_ .edge-pattern-solid{stroke-dasharray:0;}#chatgpt-mermaid-\_r_ur\_ .edge-thickness-invisible{stroke-width:0;fill:none;}#chatgpt-mermaid-\_r_ur\_ .edge-pattern-dashed{stroke-dasharray:3;}#chatgpt-mermaid-\_r_ur\_ .edge-pattern-dotted{stroke-dasharray:2;}#chatgpt-mermaid-\_r_ur\_ .marker{fill:rgb(175, 175, 175);stroke:rgb(175, 175, 175);}#chatgpt-mermaid-\_r_ur\_ .marker.cross{stroke:rgb(175, 175, 175);}#chatgpt-mermaid-\_r_ur\_ svg{font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";font-size:16px;}#chatgpt-mermaid-\_r_ur\_ p{margin:0;}#chatgpt-mermaid-\_r_ur\_ .label{font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";color:rgb(237, 237, 237);}#chatgpt-mermaid-\_r_ur\_ .cluster-label text{fill:rgb(237, 237, 237);}#chatgpt-mermaid-\_r_ur\_ .cluster-label span{color:rgb(237, 237, 237);}#chatgpt-mermaid-\_r_ur\_ .cluster-label span p{background-color:transparent;}#chatgpt-mermaid-\_r_ur\_ .label text,#chatgpt-mermaid-\_r_ur\_ span{fill:rgb(237, 237, 237);color:rgb(237, 237, 237);}#chatgpt-mermaid-\_r_ur\_ .node rect,#chatgpt-mermaid-\_r_ur\_ .node circle,#chatgpt-mermaid-\_r_ur\_ .node ellipse,#chatgpt-mermaid-\_r_ur\_ .node polygon,#chatgpt-mermaid-\_r_ur\_ .node path{fill:rgb(51, 24, 37);stroke:rgb(171, 79, 122);stroke-width:1px;}#chatgpt-mermaid-\_r_ur\_ .rough-node .label text,#chatgpt-mermaid-\_r_ur\_ .node .label text,#chatgpt-mermaid-\_r_ur\_ .image-shape .label,#chatgpt-mermaid-\_r_ur\_ .icon-shape .label{text-anchor:middle;}#chatgpt-mermaid-\_r_ur\_ .node .katex path{fill:#000;stroke:#000;stroke-width:1px;}#chatgpt-mermaid-\_r_ur\_ .rough-node .label,#chatgpt-mermaid-\_r_ur\_ .node .label,#chatgpt-mermaid-\_r_ur\_ .image-shape .label,#chatgpt-mermaid-\_r_ur\_ .icon-shape .label{text-align:center;}#chatgpt-mermaid-\_r_ur\_ .node.clickable{cursor:pointer;}#chatgpt-mermaid-\_r_ur\_ .root .anchor path{fill:rgb(175, 175, 175)!important;stroke-width:0;stroke:rgb(175, 175, 175);}#chatgpt-mermaid-\_r_ur\_ .arrowheadPath{fill:rgb(175, 175, 175);}#chatgpt-mermaid-\_r_ur\_ .edgePath .path{stroke:rgb(175, 175, 175);stroke-width:1px;}#chatgpt-mermaid-\_r_ur\_ .flowchart-link{stroke:rgb(175, 175, 175);fill:none;}#chatgpt-mermaid-\_r_ur\_ .edgeLabel{background-color:rgb(0, 0, 0);text-align:center;}#chatgpt-mermaid-\_r_ur\_ .edgeLabel p{background-color:rgb(0, 0, 0);}#chatgpt-mermaid-\_r_ur\_ .edgeLabel rect{opacity:0.5;background-color:rgb(0, 0, 0);fill:rgb(0, 0, 0);}#chatgpt-mermaid-\_r_ur\_ .labelBkg{background-color:rgba(0, 0, 0, 0.5);}#chatgpt-mermaid-\_r_ur\_ .cluster rect{fill:rgb(48, 48, 48);stroke:rgba(255, 255, 255, 0.15);stroke-width:1px;}#chatgpt-mermaid-\_r_ur\_ .cluster text{fill:rgb(237, 237, 237);}#chatgpt-mermaid-\_r_ur\_ .cluster span{color:rgb(237, 237, 237);}#chatgpt-mermaid-\_r_ur\_ div.mermaidTooltip{position:absolute;text-align:center;max-width:200px;padding:2px;font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";font-size:12px;background:rgb(48, 48, 48);border:1px solid rgba(255, 255, 255, 0.15);border-radius:2px;pointer-events:none;z-index:100;}#chatgpt-mermaid-\_r_ur\_ .flowchartTitleText{text-anchor:middle;font-size:18px;fill:rgb(237, 237, 237);}#chatgpt-mermaid-\_r_ur\_ rect.text{fill:none;stroke-width:0;}#chatgpt-mermaid-\_r_ur\_ .icon-shape,#chatgpt-mermaid-\_r_ur\_ .image-shape{background-color:rgb(0, 0, 0);text-align:center;}#chatgpt-mermaid-\_r_ur\_ .icon-shape p,#chatgpt-mermaid-\_r_ur\_ .image-shape p{background-color:rgb(0, 0, 0);padding:2px;}#chatgpt-mermaid-\_r_ur\_ .icon-shape .label rect,#chatgpt-mermaid-\_r_ur\_ .image-shape .label rect{opacity:0.5;background-color:rgb(0, 0, 0);fill:rgb(0, 0, 0);}#chatgpt-mermaid-\_r_ur\_ .label-icon{display:inline-block;height:1em;overflow:visible;vertical-align:-0.125em;}#chatgpt-mermaid-\_r_ur\_ .node .label-icon path{fill:currentColor;stroke:revert;stroke-width:revert;}#chatgpt-mermaid-\_r_ur\_ .node .neo-node{stroke:rgb(171, 79, 122);}#chatgpt-mermaid-\_r_ur\_ [data-look="neo"].node rect,#chatgpt-mermaid-\_r_ur\_ [data-look="neo"].cluster rect,#chatgpt-mermaid-\_r_ur\_ [data-look="neo"].node polygon{stroke:url(#chatgpt-mermaid-\_r_ur\_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_ur\_ [data-look="neo"].swimlane.cluster rect{filter:none;}#chatgpt-mermaid-\_r_ur\_ [data-look="neo"].node path{stroke:url(#chatgpt-mermaid-\_r_ur\_-gradient);stroke-width:1px;}#chatgpt-mermaid-\_r_ur\_ [data-look="neo"].node .outer-path{filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_ur\_ [data-look="neo"].node .neo-line path{stroke:rgb(171, 79, 122);filter:none;}#chatgpt-mermaid-\_r_ur\_ [data-look="neo"].node circle{stroke:url(#chatgpt-mermaid-\_r_ur\_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_ur\_ [data-look="neo"].node circle .state-start{fill:#000000;}#chatgpt-mermaid-\_r_ur\_ [data-look="neo"].icon-shape .icon{fill:url(#chatgpt-mermaid-\_r_ur\_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_ur\_ [data-look="neo"].icon-shape .icon-neo path{stroke:url(#chatgpt-mermaid-\_r_ur\_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-\_r_ur\_ .node text{font-size:14px;font-weight:600;letter-spacing:normal;fill:rgb(255, 186, 218);}#chatgpt-mermaid-\_r_ur\_ .edgeLabels text{font-size:13px;font-weight:600;letter-spacing:-0.08px;fill:rgb(255, 186, 218);}#chatgpt-mermaid-\_r_ur\_ .node tspan[font-weight="normal"],#chatgpt-mermaid-\_r_ur\_ .edgeLabels tspan[font-weight="normal"]{font-weight:600;}#chatgpt-mermaid-\_r_ur\_ .edgeLabel .label rect{opacity:1;rx:13px;ry:13px;fill:rgb(41, 16, 28);stroke:rgb(95, 53, 72);stroke-width:1px;}#chatgpt-mermaid-\_r_ur\_ .node rect,#chatgpt-mermaid-\_r_ur\_ .node circle,#chatgpt-mermaid-\_r_ur\_ .node ellipse,#chatgpt-mermaid-\_r_ur\_ .node polygon,#chatgpt-mermaid-\_r_ur\_ .node path{fill:rgb(77, 31, 52);stroke:rgba(255, 255, 255, 0.1);stroke-width:1px;}#chatgpt-mermaid-\_r_ur\_ .node rect{rx:16px;ry:16px;}#chatgpt-mermaid-\_r_ur\_ .node.mermaid-decision .label-container{fill:rgb(41, 16, 28);stroke:rgb(95, 53, 72);stroke-dasharray:2,2;}#chatgpt-mermaid-\_r_ur\_ .edgePaths .flowchart-link{stroke:rgb(175, 175, 175);stroke-width:1px;stroke-linecap:round;stroke-linejoin:round;}#chatgpt-mermaid-\_r_ur\_ .marker{fill:rgb(175, 175, 175);stroke:rgb(175, 175, 175);}#chatgpt-mermaid-\_r_ur\_ :root{--mermaid-font-family:-apple-system-body,ui-sans-serif,-apple-system,system-ui,"Segoe UI",Helvetica,"Apple Color Emoji",Arial,sans-serif,"Segoe UI Emoji","Segoe UI Symbol";}Start CameraCapture Frame → Flip / MirrorRun MediaPipe Pose DetectionHuman Detected?Reset TimerExtract Nose Landmark x, yInside Restricted Polygon?Reset TimerStart / Continue TimerTimer ≥ 3 Seconds?INTRUSION CONFIRMEDFlash Banner on ScreenLog to ConsoleSend SMS via TwilioStart 15s CooldownNoYesNoYesNoYes

                     Start 15s cooldown
```

**Key Detection Logic:**
1. MediaPipe extracts the **nose landmark (x, y)** as the person's position
2. `cv2.pointPolygonTest()` checks if this point is inside the restricted polygon
3. A **3-second continuous timer** confirms genuine intrusion vs. passerby
4. Alert triggers → SMS sent → **15-second cooldown** begins

---

## 📁 Project Structure

```
Intrusion-detection-system/
│
├── main.py          # Core system — detection, zone logic, visual UI
├── send.py          # Alert module — Twilio SMS integration
├── requirements.txt # All dependencies
└── README.md        # This file
```

---

## ⚙️ Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/Intrusion-detection-system.git
cd Intrusion-detection-system
```

### 2. Create Virtual Environment (Python 3.10 required)
```bash
py -3.10 -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # Mac/Linux
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure SMS Alerts (Optional)
Open `send.py` and fill in your Twilio credentials:
```python
ACCOUNT_SID = "your_twilio_account_sid"
AUTH_TOKEN  = "your_twilio_auth_token"
FROM_PHONE  = "+1xxxxxxxxxx"   # Your Twilio number
TO_PHONE    = "+91xxxxxxxxxx"  # Your personal number
```
> 💡 Skip this step if you only want visual alerts. The system works without Twilio — it just logs to console instead.

### 5. Run the System
```bash
python main.py
```

---

## 🖥️ Usage

- A window opens showing your live webcam feed
- A **yellow box** marks the restricted zone on screen
- Walk into the box — it turns **red** and starts the timer
- Stay inside for **3 seconds** → intrusion alert fires
- Press **Q** to quit

### Customizing the Restricted Zone
In `main.py`, edit the `RESTRICTED_ZONE` coordinates to reposition or resize the zone:
```python
RESTRICTED_ZONE = np.array([
    [150, 100],   # Top-left
    [500, 100],   # Top-right
    [500, 400],   # Bottom-right
    [150, 400]    # Bottom-left
], np.int32)
```

---

## 📦 Requirements

```
opencv-python
cvzone==1.6.1
mediapipe
twilio
numpy
```

> ⚠️ **Python 3.10 is required.** MediaPipe does not currently support Python 3.11+.

---

## 🚀 Future Enhancements

- [ ] Web dashboard (React + Flask) for remote monitoring
- [ ] Email alert support
- [ ] Multiple restricted zones
- [ ] Recording and saving intrusion clips
- [ ] Night vision / low-light support
- [ ] Mobile app integration

---

## 👨‍💻 Author

Anusha — B.Tech Computer Science (AI & ML)
Minor Project

---

## 📄 License

This project is licensed under the [MIT License](https://choosealicense.com/licenses/mit/).

---

## 🙏 Acknowledgements

- [cvzone by Computer Vision Zone](https://github.com/cvzone/cvzone)
- [MediaPipe by Google](https://mediapipe.dev)
- [OpenCV](https://opencv.org)
- [Twilio](https://twilio.com)
