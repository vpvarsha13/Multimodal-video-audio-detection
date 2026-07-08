# Multimodal Video-Audio Deepfake Detection

## Overview

This project presents a multimodal deepfake detection framework that combines **video** and **audio** information to classify videos as **Real** or **Fake**. Deep visual features are extracted using **VideoMAE**, while speech representations are extracted using **Wav2Vec2**. Three multimodal fusion strategies are implemented and compared:

- Early Fusion
- Late Fusion
- Hybrid Fusion

The project is implemented using the **FakeAVCeleb v1.2** dataset.

---

## Repository Structure

```
Multimodal-video-audio-detection/
│
├── multimodel-feature-extraction.ipynb
├── early-fusion.ipynb
├── late fusion.ipynb
├── hybrid-fusion.ipynb
└── README.md
```

---

## Dataset

**Dataset:** FakeAVCeleb v1.2

### Original Dataset

- Real Videos: 500
- Fake Videos: 21,060

### Balanced Dataset Used

- Real Videos: 500
- Fake Videos: 500

### Dataset Split

- Training: 640
- Validation: 160
- Testing: 200

---

## Feature Extraction

### Video Features

- Model: **VideoMAE-Base**
- Frames Extracted: 16 per video
- Output Feature Size: **768**

### Audio Features

- Model: **Wav2Vec2-Base**
- Sampling Rate: 16 kHz
- Output Feature Size: **768**

Generated feature files:

- `video_features.npy`
- `audio_features.npy`
- `labels.npy`
- `video_names.npy`

---

## Fusion Models

### Early Fusion

- Concatenates video and audio features.
- Uses a fully connected neural network for classification.

**Performance**

- Accuracy: **85.50%**
- Precision: **88.17%**
- Recall: **82.00%**
- F1-Score: **84.97%**

---

### Late Fusion

- Processes video and audio features independently.
- Combines prediction probabilities for final classification.

**Performance**

- Accuracy: **86.50%**
- Precision: **90.11%**
- Recall: **82.00%**
- F1-Score: **85.86%**

---

### Hybrid Fusion

- Combines feature-level and decision-level fusion.
- Produces a joint multimodal representation for classification.

**Performance**

- Accuracy: **88.50%**
- Precision: **85.98%**
- Recall: **92.00%**
- F1-Score: **88.89%**
- ROC-AUC: **94.40%**

---

## Technologies Used

- Python
- PyTorch
- Transformers
- VideoMAE
- Wav2Vec2
- OpenCV
- Librosa
- NumPy
- Scikit-learn
- Matplotlib

---

## Results Summary

| Model | Accuracy | Precision | Recall | F1-Score |
|--------|----------|-----------|--------|----------|
| Early Fusion | 85.50% | 88.17% | 82.00% | 84.97% |
| Late Fusion | 86.50% | 90.11% | 82.00% | 85.86% |
| Hybrid Fusion | **88.50%** | **85.98%** | **92.00%** | **88.89%** |

---

## Future Work

- Cross-dataset evaluation
- Real-time multimodal deepfake detection
- Larger benchmark datasets
- Transformer-based multimodal fusion architectures

---

## License

This project is intended for academic and research purposes.
