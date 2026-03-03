# 👕 Fashion-MNIST Deep Learning Comparative Analysis



## 📌 Brief Description
This repository contains the algorithmic implementations and evaluation metrics for a comparative study on image classification using the **Fashion-MNIST** dataset. Developed using TensorFlow and Keras, the project explores how different neural network architectures process 28x28 grayscale images, evaluating their classification accuracy, computational efficiency, and resistance to overfitting.

To ensure strict comparative validity, all models share a unified data preprocessing pipeline consisting of cleaning, 0.0-1.0 normalization, and a standardized 60k/10k train-test split.

## 📊 Dataset Origin
The Fashion-MNIST dataset utilized in this study was published by Zalando Research in 2017. It was created as a direct, more computationally challenging drop-in replacement for the original MNIST handwritten digits dataset. The dataset consists of 70,000 28x28 grayscale images extracted from Zalando's actual e-commerce clothing catalog, categorized into 10 distinct classes (e.g., T-shirts, Trousers, Sneakers). 

View the original dataset at [Zalando Research's official GitHub repository](https://github.com/zalandoresearch/fashion-mnist).

## 🧠 Architectures Evaluated
The project evaluates and contrasts five specific architectures, progressing from flat-line pixel processing to deep spatial hierarchies:

1. **Baseline MLP:** A standard multi-layer perceptron.
2. **LeNet-5:** A historic architectural implementation for standard image recognition.
3. **Shallow CNN:** A lightweight convolutional network for basic spatial feature extraction.
4. **Deep CNN:** A stacked convolutional network for learning complex, hierarchical textures.
5. **Custom Optimized CNN:** A modernized architecture utilizing Batch Normalization and aggressive Dropout rates (0.50) to heavily penalize overfitting.

## 🏆 Key Findings & Results
The implementation results demonstrated a stepwise improvement in accuracy as the models became more complex and better at handling spatial information:
* **MLP:** Achieved 88.42% accuracy. It struggled the most as it processes images as a flat 1D array, failing to understand 2D structural relationships.
* **LeNet-5 & Shallow CNN:** Reached 89.61% and 90.84% accuracy respectively, proving that introducing basic convolutional layers vastly improves spatial feature extraction.
* **Deep CNN:** Achieved 92.16% accuracy through deeper hierarchical filters.
* **Custom CNN:** Reached the highest overall accuracy at **92.68%** (and an F1-Score of 0.9272). Batch normalization and dropout layers successfully prevented this deep model from overfitting the training data.

**Conclusion:** While the Custom CNN is the definitive optimal choice for maximum predictive capability on dedicated hardware, the Shallow CNN and LeNet-5 models offer an excellent balance of speed and accuracy, making them highly suitable for computationally limited real-world applications (such as mobile scanning apps).

## 🛠️ Tech Stack
* **Language:** Python
* **Deep Learning:** TensorFlow / Keras
* **Data Manipulation:** NumPy
* **Evaluation Metrics:** Scikit-learn (Classification Reports, Confusion Matrices)
* **Data Visualization:** Matplotlib, Seaborn

## 🚀 How to Run
1. Clone this repository to your local machine.
2. Ensure you have the required libraries installed: `pip install tensorflow numpy scikit-learn matplotlib seaborn`
3. Run the Jupyter Notebook / Google Colab file to execute the unified data pipeline and train the models.
4. The script will automatically download the Fashion-MNIST dataset via `tf.keras.datasets`.
