# AI Task 1: Image Classification

This project implements an image classification model to distinguish between two classes: **iPhone** (class 0) and **Galaxy** (class 1). The model is built using Keras and TensorFlow.

## Project Structure

- **ai_task_1_image_classification.py**: The Python script for loading the model, predicting classes for images, and displaying results.
- **keras_model.h5**: Pretrained Keras model file.
- **labels.txt**: Text file containing the class labels.
- **converted_keras.zip**: Contains the necessary files, including the Keras model and other related resources.

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
```
![image](https://github.com/user-attachments/assets/ee61f4fa-0f38-4ea8-83ab-354e84773bee)
![image](https://github.com/user-attachments/assets/a9e7f701-4fda-45cd-b8ff-799617908b91)
![image](https://github.com/user-attachments/assets/9da3c8e5-3318-4264-9ac2-35a25aad7b1f)

```

## Notes
- The input images must be in RGB format.
- Ensure images are of reasonable quality for best results.
- Modify paths in the script as needed to match your environment.

## Future Work
- Expand the model to support additional classes.
- Improve preprocessing for edge cases (e.g., grayscale images).
- Integrate a web or GUI interface for easier interaction.

## License
This project is open-source and available under the MIT License.

