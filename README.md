# 🦁 Advanced Wild Animal Detection & Alert System using YOLOv5
## 🎯 Real-Time Object Detection | Human + Domestic + Wild Animals | Alarm Trigger
# Overview

This project is an Advanced Wild Animal Detection and Alert System built using YOLOv5, Python, and Streamlit.
The system can detect:

✔ Wild Animals (tiger, leopard, elephant, bear, etc.)

✔ Domestic Animals (dog, cat, cow, goat, etc.)

✔ Humans

✔ Unknown objects

# Based on the detection, the system automatically triggers:

🔊 Warning Alarm sound for wild animals

🟢 Safe notifications for humans & pets

⚠ “Unknown Object” message if object not in dataset

This helps prevent human–animal conflicts near forest borders, farms, and night surveillance systems.

# 🖥️ Development Environment
🛠 Local Development – Pycharm

Initially, I started developing this project using Pycharm.
But since my local system has no GPU, the model was extremely slow and training was impossible.

# 🖥⚡ Moved to Google Colab

To use NVIDIA Tesla T4 GPU, I switched my training and testing to Google Colab.
This greatly improved:

✔ Training speed

✔ Inference speed

✔ Model accuracy

# 📦 Dataset Preparation (Roboflow)

I used Roboflow to build and prepare the dataset:

✔ Uploaded raw images
✔ Annotated bounding boxes
✔ Auto-splitting (train/val/test)
✔ Augmentation (optional)
✔ Exported as YOLOv5 format

Dataset contains:

Wild animals

Domestic animals

Humans

Roboflow made dataset creation fast and easy.

# 🤖 Model Used – YOLOv5

I trained a custom YOLOv5 model:

Model: yolov5s

Epochs: (your number)

Classes: (wild + domestic + human)

Hardware: Google Colab (Tesla T4)

Training command:

python train.py --img 640 --batch 16 --epochs 80 --data data.yaml --weights yolov5s.pt


After training, I got the:

✔ best.pt – best performing model
✔ last.pt – final model

# 🌐 Streamlit Web App

A Streamlit interface was built for easy interaction:

Features:

📤 Upload image

🔍 Detect object (wild/ domestic / humans)

🔊 Play alarm sound for wild animals

🖼 Shows annotated prediction image

🌍 Can be accessed publicly using ngrok

Run the app:

streamlit run app.py

# 🚀 Deploying Streamlit on Colab Using ngrok

Because Streamlit cannot directly run publicly on Colab, I used ngrok:

ngrok http 8501

This gives a public URL to access the app from anywhere.

# 🛡️ Alert System Logic
Detected Object	Output
🐯 Wild Animal	🔊 Loud alarm sound + red warning
🐶 Domestic Animal	🟢 "Pet / Domestic Animal Detected"
🧍 Human	🟢 "Human Detected – Safe"
❓ Unknown	⚠ "Unknown Object"
🎥 How It Works

User uploads an image

YOLOv5 model predicts the animal/human

Based on class:

Wild animal → alarm

Pet → show name

Human → safe message

Unknown → warning text

Output image is displayed

# 🎯 Future Enhancements

📱 Android mobile app

📡 IoT-based real-time alert system

🌍 GPS-based animal tracking

🎥 Real-time CCTV camera integration

☁ Deploy on AWS/GCP

# 🙌 Acknowledgements

Ultralytics YOLOv5

Google Colab

Roboflow

Streamlit

ngrok

OpenCV

