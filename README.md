 <div align="center">

# 🎙️ AI Model Using RVC  
*A Simple and Reproducible Workflow for Voice Conversion & Audio Synthesis*

![Python](https://img.shields.io/badge/Python-3.10-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

</div>

---

## 📑 Table of Contents
- [Problem Statement](#problem-statement)
- [Use Cases](#use-cases)
- [Project Overview](#project-overview)
- [Folder Structure](#folder-structure)
- [Setup & Environment](#setup--environment)
- [Data Preparation & Processing](#data-preparation--processing)
- [Model Training & Conversion](#model-training--conversion)
- [RVC WebUI](#rvc-webui)
- [Model Inference](#model-inference)
- [Environment Maintenance](#environment-maintenance)

---

## 🧩 Problem Statement

Voice conversion and audio synthesis can be complex and time-consuming.  
This project provides a **simple, reproducible workflow using RVC (Retrieval-based Voice Conversion)**  
to train, convert, and experiment with voice models efficiently.

---

## 🎯 Use Cases

1. **Voice Conversion** – Transform recordings to sound like a different speaker.  
2. **Multilingual Audio Synthesis** – Generate speech in multiple languages while preserving tone.  
3. **Audio Experimentation & Research** – Analyze pitch, timbre, and voice quality.  
4. **Content Creation & Entertainment** – Produce voiceovers for videos, animations, or games.  
5. **Accessibility & Assistive Tools** – Generate voice outputs for people with speech impairments.  

---

## 🧠 Project Overview

A project for **training, converting, and experimenting** with voice models using **RVC technology**.  
It’s designed to simplify audio synthesis with clear step-by-step commands and reproducible workflows.

### This repository demonstrates:
- Setting up Python environments  
- Preprocessing audio datasets  
- Training RVC voice conversion models  
- Converting audio with RVC WebUI  
- Best practices for reproducibility and organization  

---

## 🗂️ Folder Structure

.venv/ # Python virtual environment
chunks/ # Processed dataset chunks
fairseq/ # Optional (remove unless needed)
Retrieval-based-Voice-Conversion-WebUI/ # Main RVC frontend and scripts
rvc_gpu_env/ # GPU training/inference scripts
somali_dataset_backup/ # Original/backup Somali language dataset
cleaned.wav # Preprocessed input audio
converted.wav # Output after conversion
data.ipynb / data.py # Supporting scripts and notebooks

<img width="354" height="362" alt="folder" src="https://github.com/user-attachments/assets/d7c36d37-6a4a-4ad5-80f5-91510d17ffdf" />



---

## ⚙️ Setup & Environment


# Create virtual environment

```bash
python -m venv .venv
```

# Activate venv (Windows)
```bash
.\.venv\Scripts\activate
```

# Activate venv (Linux/Mac)
```bash
source .venv/bin/activate
```

# Install dependencies
```bash
pip install -r requirements.txt
```

🌐 RVC WebUI
```bash
# Launch RVC Web Interface
python Retrieval-based-Voice-Conversion-WebUI/infer-web.py
```

🎨 RVC WebUI Screenshot

🧹 Data Preparation & Processing
```bash
# Preprocess and clean raw audio data
python data.py --input somali_dataset_backup/raw/ --output cleaned.wav
```

##📸 Preprocessing Image
<img src="https://github.com/user-attachments/assets/493f517f-995b-488a-b7f3-5d834b3ba1ef" alt="Preprocessing" width="800"/>



# Feature extraction for training (pitch extraction, etc.)
```bash
python extract_f0_feature.py --input somali_dataset_backup/ --output chunks/
```

##📸 Feature Extraction Image
<img width="1868" height="346" alt="feature extraction" src="https://github.com/user-attachments/assets/97c9c300-9058-4163-b9fe-daa4767ae417" />


##🧩 Model Training & Conversion (RVC)

```bash
# Example training command for RVC
python train.py --exp_name exp_somali --dataset chunks/ --output_dir models/ --epochs 100 --gpu 0
```

## 📸 Model Training Image  
<img src="https://github.com/user-attachments/assets/db4c3202-e791-48f4-b3af-5106bfecfeb8" alt="Training Screenshot" width="800"/>  

Trining Done:

<img width="958" height="891" alt="training2" src="https://github.com/user-attachments/assets/fb101320-af09-4664-9884-f3b1de147600" />



Notes:
```bash
--exp_name → any custom experiment name (e.g., exp_somali)

--dataset → path to your extracted features

--output_dir → location for models and logs

--epochs → number of training passes

--gpu → specify which GPU to use
```

🔊 Model Inference
```bash
# Convert your preprocessed audio using trained model
python Retrieval-based-Voice-Conversion-WebUI/infer.py \
--input cleaned.wav \
--model <your_model>.pth \
--output converted.wav
```

##📸 Model Inference Image
<img width="1817" height="1023" alt="inference" src="https://github.com/user-attachments/assets/813e4f24-30b4-4443-8721-fd5d90793012" />


🧽 Environment Maintenance
# Clean workspace (Windows PowerShell)
```bash
powershell -Command "Get-ChildItem -Path . -Recurse -Directory -Filter __pycache__ | Remove-Item -Recurse -Force"
```


## 🔈 Output Audio

🎧 # Listen to the Audio

<audio controls>
  <source src="assets/audio.wav" type="audio/wav">
  Your browser does not support the audio element.
</audio>




