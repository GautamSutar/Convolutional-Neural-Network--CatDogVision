# 🐾 **CatDogVision Lite – CNN Image Classifier**

> 🧠 A deep learning project that classifies images of cats and dogs using a Convolutional Neural Network (CNN) built with TensorFlow and Keras.

---

## 🌟 **Overview**

**CatDogVision Lite** is a beginner-friendly deep learning project that trains a **Convolutional Neural Network (CNN)** to identify whether an image contains a **cat 🐱** or a **dog 🐶**.
This project focuses purely on **data preprocessing, model training, evaluation, and single-image prediction** — a perfect foundation for beginners before moving to deployment.

---

## ⚙️ **Project Features**

✅ Image preprocessing using `ImageDataGenerator`
✅ CNN architecture built with TensorFlow and Keras
✅ Binary classification (Cat vs Dog)
✅ Real-time single image prediction
✅ Simple, clean, and easy to run

---

## 🧰 **Tech Stack**

| Category             | Tools / Libraries    |
| -------------------- | -------------------- |
| Programming Language | 🐍 Python            |
| Deep Learning        | 🤖 TensorFlow, Keras |
| Data Handling        | 🔢 NumPy, Pillow     |

---

## 🗂️ **Dataset Structure**

```
dataset/
├── training_set/
│   ├── cats/
│   └── dogs/
├── test_set/
│   ├── cats/
│   └── dogs/
└── single_prediction/
    └── cat_or_dog_1.jpg
```

> 📦 You can use a public dataset like [Kaggle Cats and Dogs Dataset](https://www.kaggle.com/datasets/tongpython/cat-and-dog).

---

## 🛠️ **Installation**

1. Clone the repository:

   ```bash
   git clone https://github.com/GautamSutar/Convolutional-Neural-Network--CatDogVision
   cd Convolutional-Neural-Network--CatDogVision

   ```

2. Install the required dependencies:

   ```bash
   pip install tensorflow numpy pillow
   ```

---

## ▶️ **How to Run**

### **1. Train the Model**

Run the main Python file:

```bash
python catdogvision.py
```

This will:

* Preprocess and augment your images
* Build and train the CNN model
* Display training and validation accuracy per epoch

---

### **2. Predict a New Image**

Once training is complete, test the model on a new image:

```python
python predict.py
```

Make sure your image is located at:

```
dataset/single_prediction/cat_or_dog_1.jpg
```

---

## 💡 **Expected Output**

After running prediction:

```
🐶 Prediction: This image is a Dog!
```

or

```
🐱 Prediction: This image is a Cat!
```

---

## 📘 **Code Overview**

### 🧩 Model Summary

```python
cnn = tf.keras.models.Sequential()
cnn.add(tf.keras.layers.Conv2D(filters=32, kernel_size=3, activation='relu', input_shape=[64, 64, 3]))
cnn.add(tf.keras.layers.MaxPool2D(pool_size=2, strides=2))
cnn.add(tf.keras.layers.Conv2D(filters=32, kernel_size=3, activation='relu'))
cnn.add(tf.keras.layers.MaxPool2D(pool_size=2, strides=2))
cnn.add(tf.keras.layers.Flatten())
cnn.add(tf.keras.layers.Dense(units=128, activation='relu'))
cnn.add(tf.keras.layers.Dense(units=1, activation='sigmoid'))
```

### 🧮 Compilation and Training

```python
cnn.compile(optimizer='adam', loss='binary_crossentropy', metrics=['accuracy'])
cnn.fit(x=training_set, validation_data=test_set, epochs=25)
```

### 🔍 Prediction Logic

```python
test_image = image.load_img('dataset/single_prediction/cat_or_dog_1.jpg', target_size=(64, 64))
test_image = image.img_to_array(test_image)
test_image = np.expand_dims(test_image, axis=0)
result = cnn.predict(test_image)

if result[0][0] == 1:
    prediction = 'dog'
else:
    prediction = 'cat'
print(prediction)
```

---

## 📄 **License**

This project is licensed under the **MIT License** — free to use and modify for learning or personal projects.

---

## 💬 **Feedback**

If this project helped you, consider giving it a ⭐ on GitHub!
For questions or collaboration, feel free to connect.

📧 *Email:* [gautamsutar.in@gmail.com](gautamsutar.in@gmail.com)
🐙 *GitHub:* [https://github.com/GautamSutar/Convolutional-Neural-Network--CatDogVision.git](https://github.com/GautamSutar/Convolutional-Neural-Network--CatDogVision.git)
