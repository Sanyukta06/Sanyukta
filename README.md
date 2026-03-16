# VisionExtract: Subject Isolation using COCO Dataset
## Overview

VisionExtract is a deep learning project that performs **automatic subject isolation from images using semantic segmentation**.

The system uses a **U-Net architecture with a ResNet34 encoder** trained on the **COCO 2017 dataset** to detect objects and separate them from the background.

The model generates a **binary segmentation mask** for each input image. This mask is then applied to remove the background and isolate the subject.

---

# Features

* Automatic subject extraction from images
* Semantic segmentation using U-Net
* COCO dataset integration
* Data augmentation for better model generalization
* Visualization of predictions
* Background removal using predicted masks

---

# Project Pipeline

1. Download the COCO 2017 dataset
2. Load annotations using PyCOCOTools
3. Generate segmentation masks from annotations
4. Apply data augmentation
5. Create a custom PyTorch dataset
6. Train a U-Net segmentation model
7. Evaluate model using validation data
8. Visualize predicted segmentation masks
9. Isolate subjects from images using predicted masks

---

# Model Architecture

The project uses **U-Net with a ResNet34 encoder**.

### Encoder

The encoder extracts deep features from the input image using convolutional layers.
ResNet34 captures complex image features such as edges, textures, and object shapes.

### Bottleneck

The bottleneck connects the encoder and decoder and represents the compressed feature representation of the image.

### Decoder

The decoder upsamples the features and reconstructs the segmentation mask using skip connections.

### Output Layer

The final layer produces a **binary segmentation mask** where:

* **1** = Subject (Foreground)
* **0** = Background

---

# Dataset

The project uses the **COCO 2017 dataset (Common Objects in Context)**.

Dataset includes:

* Training images
* Validation images
* Instance segmentation annotations

COCO contains **80+ object categories with detailed segmentation masks**.

Dataset website:

https://cocodataset.org

---

# Technologies Used

* Python
* PyTorch
* segmentation-models-pytorch
* PyCOCOTools
* Albumentations
* OpenCV
* Matplotlib
* Google Colab

---

# Installation

Clone the repository:

```bash
git clone https://github.com/your-username/visionextract.git
cd visionextract
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Or install manually:

```bash
pip install torch torchvision
pip install pycocotools
pip install albumentations
pip install segmentation-models-pytorch
pip install opencv-python
pip install matplotlib
pip install tqdm
pip install scikit-learn
pip install kagglehub
pip install torchmetrics
```

---

# How to Run

### Step 1

Open the notebook in **Google Colab or Jupyter Notebook**.

### Step 2

Run the installation cell to install required libraries.

### Step 3

Download the COCO dataset automatically using `kagglehub`.

### Step 4

Run the training cells to train the U-Net segmentation model.

### Step 5

Visualize prediction results including:

* Input Image
* Ground Truth Mask
* Predicted Mask
* Isolated Subject

---

# Example Output

Below is an example of subject isolation.

| Input Image | Predicted Mask | Isolated Subject   |
| ----------- | -------------- | ------------------ |
| Image       | Mask           | Background Removed |

Example visualization:

```
Original Image → Predicted Mask → Background Removed Output
```

---

# Evaluation Metrics

Model performance is evaluated using:

### Intersection over Union (IoU)

Measures overlap between predicted mask and ground truth mask.

### Dice Score

Measures similarity between predicted segmentation mask and ground truth mask.

Higher scores indicate better segmentation performance.

---

# Project Structure

```
visionextract/
│
├── notebooks/
│   └── milestone2.ipynb
│
├── src/
│   ├── dataset.py
│   ├── model.py
│   ├── train.py
│   └── visualize.py
│
├── outputs/
│   └── sample_results.png
│
├── requirements.txt
│
└── README.md
```

---

# Future Improvements

* Train on larger datasets
* Improve segmentation accuracy
* Add real-time inference
* Deploy as a web application
* Implement instance-level segmentation

---

# Applications

* Background removal
* Photo editing tools
* Autonomous systems
* Medical image segmentation
* Image preprocessing pipelines

---

