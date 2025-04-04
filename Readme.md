# DeepFake Detection using Feature Stacking and Meta-Learning

## **Project Overview**
DeepFake videos pose a serious threat to digital security and misinformation. This project aims to detect deepfake videos using an ensemble feature-stacking approach with CNN models like **Xception**, **EfficientNet-B7**, and **Multi-Layer Perceptron (MLP)** as a meta-learner. The dataset is preprocessed using **RetinaFace** to extract faces from videos before classification.

---

## **Dataset Sources**
### **1. Original Dataset (Raw Videos)**
- **Celeb-DF (V2)** from Kaggle
- Download using:
  ```python
  !pip install kaggle
  !mkdir -p ~/.kaggle
  !echo '{"username":"YOUR_USERNAME","key":"YOUR_KAGGLE_API_KEY"}' > ~/.kaggle/kaggle.json
  !chmod 600 ~/.kaggle/kaggle.json
  !kaggle datasets download -d reubensuju/celeb-df-v2
  !unzip celeb-df-v2.zip -d CelebDF
  ```
- [Dataset Link](https://www.kaggle.com/datasets/reubensuju/celeb-df-v2)

### **2. Preprocessed Dataset (Faces Extracted from Videos)**
- Available on **AWS S3** (Preprocessed Faces)
- Contains: `train`, `test`, `validate` folders each having `real` and `fake` subfolders
- Download:
  ```sh
  wget https://deep-fake-dataset.s3.eu-north-1.amazonaws.com/PreprocessedDatasetV1.zip
  unzip PreprocessedDatasetV1.zip
  ```

---

## **Model Architecture**
The model follows a **feature stacking ensemble approach**:
1. **Xception** - Extracts deep features from images
2. **EfficientNet-B7** - Extracts additional feature representations
3. **Feature Selection** - Ranking-based selection to reduce redundant features
4. **Meta-Learner (MLP)** - Uses selected features to classify Real vs Fake videos

---


## **Installation & Setup**
### **1. Clone the Repository**
```sh
git clone https://github.com/aayushshah1/DeepfakeDetector.git
cd DeepfakeDetector
```

### **2. Install Dependencies**
```sh
pip install -r requirements.txt
```

### **3. Download Preprocessed Dataset**
```sh
wget https://deep-fake-dataset.s3.eu-north-1.amazonaws.com/PreprocessedDatasetV1.zip
unzip PreprocessedDatasetV1.zip
```

### **4. Train the Model**
Run the **Jupyter Notebook**:
```sh
jupyter notebook
```
Open `Main.ipynb` and execute all cells.

---

## **License**
This project is open-source under the **MIT License**.

---

## **References**
- Paper: **Deepfake Detection using Deep Feature Stacking and Meta-Learning**
- Authors: Gourab Naskar, Sk Mohiuddin, Samir Malakar, Erik Cuevas, Ram Sarkar
- [Paper Link](https://www.sciencedirect.com/science/article/pii/S2666539124001234)

