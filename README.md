![image](https://github.com/user-attachments/assets/4f377c52-1b79-41dc-a694-40ae2ae16e4a)# Smartphone Image Classification

This project implements an image classification model to distinguish between two classes: **iPhone** (class 0) and **Galaxy** (class 1). The model is built using Keras and TensorFlow.

## Project Structure

- **ai\_task\_1\_image\_classification.py**: The Python script for loading the model, predicting classes for images, and displaying results.
- **keras\_model.h5**: Pretrained Keras model file.
- **labels.txt**: Text file containing the class labels.
- **test.zip**: Archive containing test images used for evaluation.

## Prerequisites

### Libraries and Dependencies

Ensure the following libraries are installed:

- TensorFlow
- Keras
- Pillow
- NumPy
- Matplotlib

Install these using pip:

```bash
pip install tensorflow keras pillow numpy matplotlib
```

### Files

Place the following files in the appropriate directory:

- `keras_model.h5`: The trained model file.
- `labels.txt`: A file with class names (each class on a new line).
- `test`: A directory containing test images.

## How to Use

### 1. Load the Model

The script automatically loads the pretrained model and the class labels:

```python
model = load_model("/content/keras_model.h5", compile=False)
with open("/content/labels.txt", "r") as file:
    class_names = file.readlines()
```

### 2. Predict an Image

The `predict_image` function takes an image path as input, preprocesses the image, and predicts its class. Example usage:

```python
predict_image("/path/to/your/image.jpg")
```

#### Steps Performed:

- Image is resized to 224x224.
- Image is normalized to the range [-1, 1].
- Model predicts the class and confidence score.

### 3. Batch Testing

To test multiple images, add their paths to the `image_paths` list:

```python
image_paths = ["/path/to/image1.jpg", "/path/to/image2.png"]
```

The script will loop through each image and display the results.

## Example Output
![Sample Prediction](https://github.com/user-attachments/assets/785113f3-cd12-4475-b1cb-d3e1452e65e4)
```
Testing image: /content/3853858281.jpg
1/1 [==============================] - 1s 1s/step
Class: 0 iphone
Confidence Score: 0.97066194
```
![image](https://github.com/user-attachments/assets/1b6a5ef7-60b6-4ef4-a878-720dfac7a3da)

```
Testing image: /content/1200px-IPhone_8_vector.svg.png
1/1 [==============================] - 0s 49ms/step
Class: 0 iphone
Confidence Score: 0.9841287
```
![image](https://github.com/user-attachments/assets/77eb91b7-89b8-4779-9fb5-965dc3ece0cc)

```
Testing image: /content/Screenshot 2024-08-20 at 10.26.20 PM.png
1/1 [==============================] - 0s 80ms/step
Class: 1 Galaxy
Confidence Score: 0.99994195

```

These are the correct results based on the provided model and test images.

## Notes

- The input images must be in RGB format.
- Ensure images are of reasonable quality for best results.
- Modify paths in the script as needed to match your environment.

## Future Work

- Expand the model to support additional classes.
- Improve preprocessing for edge cases (e.g., grayscale images).
- Integrate a web or GUI interface for easier interaction.


