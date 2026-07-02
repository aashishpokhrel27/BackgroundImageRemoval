# Background Image Removal

**Undergraduate Thesis Project · Tribhuvan University · Bachelor of Engineering in Computer Engineering · 2021**

A full-stack web application for automatic background removal from images using deep learning. Users upload an image through a browser interface; the backend runs a segmentation model and returns the image with the background removed.

---

## Overview

Background removal is a foundational computer vision task with applications in e-commerce, portrait photography, video conferencing, and document processing. This project delivers an end-to-end solution — from deep learning inference to a usable web interface — built as my final year undergraduate thesis.

**What it does:**
- Accepts an image upload via a browser-based frontend
- Sends the image to a Python backend running a deep learning segmentation model
- Returns the foreground-extracted image with background removed
- Displays the result instantly in the browser

---

## Architecture

```
┌─────────────────────────────────────┐
│           Frontend                  │
│   HTML + CSS + JavaScript           │
│   Image upload UI + result display  │
└────────────────┬────────────────────┘
                 │  HTTP (image upload / response)
                 ▼
┌─────────────────────────────────────┐
│            Backend                  │
│   Python (Flask / FastAPI)          │
│   Deep learning segmentation model  │
│   Background removal inference      │
└─────────────────────────────────────┘
```

The backend loads a pretrained segmentation model, processes the uploaded image, generates a binary foreground mask, and applies it to return a clean PNG with transparent background.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript |
| Backend | Python |
| ML/CV | Deep learning segmentation model |
| Interface | REST API (image upload → masked output) |

---

## Project Structure

```
BackgroundImageRemoval/
├── backend/        # Python backend — ML inference + API server
├── frontend/       # HTML/CSS/JS — upload UI and result display
├── .gitignore
└── README.md
```

---

## Setup & Usage

**Prerequisites**
```
Python 3.8+
Node.js (optional, for frontend dev server)
```

**Backend**
```bash
git clone https://github.com/aashishpokhrel27/BackgroundImageRemoval.git
cd BackgroundImageRemoval/backend
pip install -r requirements.txt
python app.py
```

**Frontend**

Open `frontend/index.html` in your browser, or serve it locally:
```bash
cd frontend
python -m http.server 3000
# Visit http://localhost:3000
```

---

## Context

This project was completed in 2021 as my undergraduate thesis at Tribhuvan University, where I graduated with a 3.7 GPA in Computer Engineering. It was my first end-to-end computer vision system — combining deep learning inference with a deployable web interface.

The work here laid the foundation for my current research on Vision-Language Models at the University of Wyoming, where I have since published at CVPR 2026 (GRAIL-V Workshop) and ICPR 2026 on negation understanding in multimodal retrieval systems.

---

## Author

**Aashish Pokhrel**  
MS Computer Science · University of Wyoming (GPA: 4.0) · Graduating May 2027  
[LinkedIn](https://linkedin.com/in/aashishpokhrel) · [Portfolio](https://aashishpokhrel27.github.io/) · [GitHub](https://github.com/aashishpokhrel27)
