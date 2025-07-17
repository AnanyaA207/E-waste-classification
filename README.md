<h1 align="center">📱 E-Waste Classification</h1>

## 🚀 Installation

```bash
!pip install -q tensorflow gradio
```

---

📥 **Dataset Download:** [Click here to access the E-Waste Image Dataset on Kaggle](https://www.kaggle.com/datasets/akshat103/e-waste-image-dataset)

## 🧾 Project Structure

```plaintext
📁 E waste data
│
├── 📁 modified-dataset
│   ├── 📁 train
│   ├── 📁 val
│   └── 📁 test
│
└── 🧠 Notebook (.ipynb or .py script)
```

---

## 🧠 Model Overview

- **Architecture:** MobileNetV3Large (with fine-tuning)
- **Input Size:** 256x256 RGB images
- **Classes (10 total):**

<div align="center">

| 🗂 Class Name    | ♻️ Description                          |
|------------------|------------------------------------------|
| Battery          | Hazardous waste                         |
| Keyboard         | Recyclable plastic + PCB                |
| Microwave        | Recyclable metal appliance              |
| Mobile           | Contains valuable metals                |
| Mouse            | Plastic + electronic                    |
| PCB              | Precious metals + toxins                |
| Player           | Motors, speakers, plastic               |
| Printer          | Cartridges + plastic body               |
| Television       | CRT/LED disposal protocols              |
| Washing Machine  | Heavy e-waste with motors               |

</div>

---

## 🔍 Features

- ✅ Real-time image classification
- 🧠 Transfer learning with MobileNetV3Large
- ✨ Custom data augmentation
- 📊 Accuracy/loss visualization
- 🧾 Auto-generated e-waste disposal tips
- 🌐 Gradio web UI

---

## 🧪 Dataset Handling

Images are loaded using:

```python
tf.keras.utils.image_dataset_from_directory(
    directory_path,
    image_size=(256, 256),
    batch_size=32,
    label_mode='categorical'
)
```

Includes training, validation, and testing splits.

---

## 🎨 Data Augmentation

Augmentation layer built using `tf.keras.Sequential`:

```python
RandomFlip, RandomRotation, RandomZoom, RandomContrast,
RandomBrightness, RandomTranslation
```

Improves generalization & mimics real-world conditions.

---

## 🛠️ Model Training

- 📦 **Loss Function:** CategoricalCrossentropy with label smoothing
- ⚙️ **Optimizer:** Adam (lr = 1e-4)
- 🛑 **Callback:** EarlyStopping (patience = 3)
- 🔁 **Epochs:** 20
- 🔍 **Eval:** Accuracy + Confusion Matrix + Classification Report

---

## 📈 Visual Results

| 📊 Metric              | 💡 Insights                        |
|------------------------|-----------------------------------|
| **Accuracy Curve**     | Tracks model performance          |
| **Loss Curve**         | Detects overfitting               |
| **Confusion Matrix**   | Shows per-class precision         |
| **Classification Report** | Precision, recall, F1-score   |

---

## 📈 Accuracy Vs Loss curve

<img width="1220" height="597" alt="Screenshot 2025-07-17 140500" src="https://github.com/user-attachments/assets/a6943cdd-04c8-4019-8c32-d62a33e3fec2" />


## Classification Report

<img width="465" height="301" alt="Picture3" src="https://github.com/user-attachments/assets/f01d9767-8b9f-4f9c-a3f9-254951d8bf05" />

---

## Confusion Matrix

<img width="403" height="306" alt="Picture2" src="https://github.com/user-attachments/assets/22b3506c-aeb0-45df-a36d-68917d515d71" />

---

## 🌐 Gradio App

<img width="1034" height="520" alt="Picture1" src="https://github.com/user-attachments/assets/3c2de5d7-aebf-4b5e-ac5b-9911ab69c8d7" />

Upload an image → Get prediction → Get **sorting instructions** instantly.

---

## 🔚 Conclusion

This project blends deep learning and environmental consciousness, helping users **identify**, **sort**, and **safely dispose** of e-waste.

---

## 💡 Future Plans

- 📦 Add more waste categories
- 📷 Object detection for multiple items

