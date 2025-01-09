# Smartphone Image Classification

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

![image](https://github.com/user-attachments/assets/aa566040-451f-4bea-a693-58932ec3cb45)
![image](https://github.com/user-attachments/assets/efed10fd-c2c2-4a5c-bf9f-553c1cd3deaf)
![image](https://github.com/user-attachments/assets/2e27f0fa-afc2-4e3a-8ab8-2e94d3ccde58)

These are the correct results based on the provided model and test images.

## Notes

- The input images must be in RGB format.
- Ensure images are of reasonable quality for best results.
- Modify paths in the script as needed to match your environment.

## Future Work

- Expand the model to support additional classes.
- Improve preprocessing for edge cases (e.g., grayscale images).
- Integrate a web or GUI interface for easier interaction.


