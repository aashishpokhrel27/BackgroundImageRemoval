# Background Image Removal

**Undergraduate Thesis Project · Tribhuvan University · Bachelor of Engineering in Computer Engineering**

A deep learning pipeline for automatic background segmentation and removal from images, trained and evaluated on standard benchmarks. This project was completed as my final year thesis (GPA: 3.7) and represents my first end-to-end implementation of a computer vision system.

---

## Overview

Background removal is a foundational computer vision task with applications in e-commerce, portrait photography, video conferencing, and content creation. This project implements a semantic segmentation approach to separate foreground subjects from background with pixel-level precision.

**Key contributions:**
- End-to-end training pipeline from data preprocessing through inference
- Evaluation on standard segmentation benchmarks
- Clean inference interface for single-image and batch processing

---

## Architecture

The system uses an encoder-decoder architecture for semantic segmentation:

```
Input Image
     │
     ▼
┌─────────────┐
│   Encoder   │  ← Pretrained CNN backbone (feature extraction)
│  (Backbone) │
└─────────────┘
     │
     ▼
┌─────────────┐
│   Decoder   │  ← Upsampling + skip connections
│  (U-Net)    │
└─────────────┘
     │
     ▼
Binary Segmentation Mask → Masked Output Image
```

---

## Setup

**Requirements**
```
Python 3.8+
PyTorch >= 1.9
torchvision
Pillow
numpy
matplotlib
```

**Install dependencies**
```bash
git clone https://github.com/aashishpokhrel27/BackgroundImageRemoval.git
cd BackgroundImageRemoval
pip install -r requirements.txt
```

---

## Usage

**Single image inference**
```python
from model import BackgroundRemover

remover = BackgroundRemover(weights='checkpoints/model.pth')
output = remover.remove_background('input.jpg')
output.save('output.png')
```

**Batch processing**
```bash
python inference.py --input_dir ./images --output_dir ./results
```

---

## Results

| Metric | Score |
|---|---|
| Mean IoU | *reported in thesis* |
| Pixel Accuracy | *reported in thesis* |

Sample outputs are available in the `/results` directory.

---

## Project Structure

```
BackgroundImageRemoval/
├── model/              # Model architecture definitions
├── data/               # Dataset loading and preprocessing
├── train.py            # Training script
├── inference.py        # Inference pipeline
├── evaluate.py         # Evaluation metrics
├── checkpoints/        # Saved model weights
├── results/            # Sample outputs
└── requirements.txt
```

---

## Context

This project was completed in 2021 as my undergraduate thesis at Tribhuvan University. It marked the beginning of my journey into computer vision — a path that has since led to research on Vision-Language Models, two publications at CVPR 2026 and ICPR 2026, and ongoing work on negation understanding in multimodal systems.

---

## Author

**Aashish Pokhrel**  
[LinkedIn](https://linkedin.com/in/aashishpokhrel) · [Portfolio](https://aashishpokhrel.com) · [Google Scholar](https://scholar.google.com/citations?user=YOUR_ID)
