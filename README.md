# ✈️ Plane Model Type Identifier

> A deep learning image classifier that identifies commercial aircraft models from photos — built as a final project for ID Tech.

---

## 🧠 Overview

This project uses a Convolutional Neural Network (CNN) trained on thousands of aircraft images to classify commercial plane models. Given a photo of an airplane, the model predicts what type it is — for example, a Boeing 737, Airbus A380, or Cessna 172.

Built with Python and TensorFlow/Keras, this project covers the full machine learning pipeline: data collection, preprocessing, model training, evaluation, and inference.

---

## 🚀 Features

- Classifies multiple commercial and general aviation aircraft types
- CNN-based image classification model
- Simple prediction script — just point it at any plane image
- Trained and evaluated with accuracy/loss visualizations
- Lightweight and easy to run locally

---

## 📁 Project Structure

```
Plane/
├── model/
│   └── plane_model.h5        # Trained Keras model
├── data/
│   ├── train/                # Training images (organized by class)
│   └── test/                 # Test images
├── train.py                  # Model training script
├── predict.py                # Run inference on a single image
├── evaluate.py               # Model evaluation & metrics
├── requirements.txt          # Python dependencies
└── README.md
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.x | Core language |
| TensorFlow / Keras | Model building & training |
| NumPy | Data manipulation |
| Matplotlib | Training visualizations |
| Pillow (PIL) | Image preprocessing |

---

## ⚙️ Setup & Installation

**1. Clone the repository**
```bash
git clone https://github.com/daniel061210/Plane.git
cd Plane
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. (Optional) Download the dataset**

Place training images in `data/train/<class_name>/` and test images in `data/test/<class_name>/`.

---

## 🏋️ Training the Model

```bash
python train.py
```

This will train the CNN on your dataset and save the model to `model/plane_model.h5`. Training progress and accuracy/loss curves will be displayed after completion.

---

## 🔍 Running a Prediction

```bash
python predict.py --image path/to/your/plane.jpg
```

The model will output the predicted aircraft type along with its confidence score.

**Example output:**
```
Predicted: Boeing 737
Confidence: 94.2%
```

---

## 📊 Model Performance

| Metric | Value |
|--------|-------|
| Training Accuracy | ~XX% |
| Validation Accuracy | ~XX% |
| Loss | ~X.XX |

> Replace the placeholder values above with your actual results after training.

---

## 🛩️ Supported Aircraft Classes

- Boeing 737
- Boeing 747
- Boeing 777
- Airbus A320
- Airbus A380
- Cessna 172
- *(add more as applicable)*

---

## 📌 Future Improvements

- Add a web interface using Flask or Streamlit for drag-and-drop predictions
- Expand the dataset with more aircraft types and edge cases
- Experiment with transfer learning (e.g., ResNet, EfficientNet) for higher accuracy
- Deploy as a mobile app or REST API

---

## 👤 Author

**Daniel** — [daniel061210](https://github.com/daniel061210)

*ID Tech Final Project — 2026*

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
