<h1 align="center">📱 Smart E-Waste Classifier</h1>
<p align="center">Deep learning meets sustainability — Classify e-waste images and get instant, eco-friendly disposal instructions ♻️</p>

---

## 🚀 Installation

```bash
!pip install -q tensorflow gradio
```

---

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

## 🌐 Gradio App

<p align="center">
  <img src="https://media.giphy.com/media/3o7buirYcmV5nSwIRW/giphy.gif" width="300"/>
</p>

Upload an image → Get prediction → Get **sorting instructions** instantly.

### 💬 Output Sample

```markdown
## 🧠 Prediction Result
Item: `Mobile`
Confidence: `0.98`

---

## ♻️ Sorting Instructions
👉 Backup data and perform a factory reset  
👉 Remove SIM and SD card  
👉 Drop off at recycling center  
👉 Valuable metals inside — do not trash  
👉 Cashback/exchange programs available  
```

---

## 🧪 Launch the App

```python
demo.launch()
```

Interactive interface with:
- 📸 Upload support
- 🧠 Auto classification
- 📝 Formatted markdown output

---

## 🔚 Conclusion

> This project blends deep learning and environmental consciousness — helping users **identify**, **sort**, and **safely dispose** of e-waste.

---

## 💡 Future Plans

- 🌍 Deploy on Hugging Face / Streamlit
- 🌐 Multilingual instructions
- 📦 Add more waste categories
- 📷 Object detection for multiple items

---

## 🤝 Credits

Made with ❤️ by **Ananya**  
Powered by **TensorFlow**, **Gradio**, and a mission to make tech cleaner.

---
