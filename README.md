Animal Image Classification Using CNN and Deep Learning
Project Overview
This project classifies an image as either a cat or a dog using deep learning and computer vision. It is designed to run in Google Colab and uses TensorFlow/Keras with a pretrained MobileNetV2 convolutional neural network (CNN) and dense neural network layers for classification.
Note: This is image classification, not object detection with bounding boxes. The model predicts one class for the uploaded image.

Objectives
- Load and preprocess cat and dog images.
- Use a pretrained CNN to extract visual features.
- Train a dense neural-network classifier.
- Evaluate performance on a validation dataset.
- Plot training/validation accuracy and loss.
- Upload an image and display the predicted class and model confidence.
Technologies Used
- Python
- TensorFlow and Keras
- MobileNetV2 (pretrained CNN)
- NumPy
- Matplotlib
- Pillow (PIL)
- Requests
- Google Colab
Model Architecture
1. Input: RGB image resized to 160 × 160 pixels.
2. Rescaling: Normalizes pixel values to the range expected by MobileNetV2.
3. CNN feature extractor: Pretrained MobileNetV2 with its weights frozen.
4. Global average pooling: Summarizes extracted feature maps.
5. Dense layer: 128 neurons with ReLU activation.
6. Dropout: Helps reduce overfitting.
7. Output layer: One sigmoid unit for binary classification (cat or dog).
The model is compiled with the Adam optimizer and binary cross-entropy loss.
Dataset
The notebook downloads and extracts the cats_and_dogs_filtered dataset. It contains separate training and validation folders.

Expected directory structure:
cats_and_dogs_filtered/
├── train/
│   ├── cats/
│   └── dogs/
└── validation/
    ├── cats/
    └── dogs/
The dataset URL used in the notebook is:

https://storage.googleapis.com/tensorflow-1-public/course2/cats_and_dogs_filtered.zip

If the download fails, check whether the URL is accessible from your Colab runtime and use the TensorFlow transfer-learning tutorial to find an available dataset source.
How to Run in Google Colab
1. Open Google Colab.
2. Create a new notebook.
3. Copy the project code into separate cells in the order provided.
4. Run the library-import cell.
5. Download and extract the dataset.
6. Load and preprocess the images.
7. Build the CNN and dense classifier.
8. Train the model.
9. Evaluate validation loss and accuracy.
10. Plot the training curves.
11. Upload a cat or dog image to test a prediction.
12. Save and download the trained model.
A GPU can make training faster. In Colab, select Runtime → Change runtime type → T4 GPU, if available.
Results
The notebook reports:
- Validation loss
- Validation accuracy
- Training and validation accuracy curves
- Training and validation loss curves
- Predicted label and confidence for an uploaded image
Actual metrics depend on the runtime, training configuration, and dataset. Record the values printed by your own run rather than assuming a particular accuracy.
Project Structure
animal-image-classification/
├── README.md
└── animal_detection_cnn.ipynb
Save your Google Colab notebook as animal_detection_cnn.ipynb if you want to keep the suggested project structure.
Limitations
- The model classifies an image as a cat or dog; it does not draw bounding boxes or detect multiple objects.
- Confidence is the model's output score, not a guarantee that the prediction is correct.
- Images outside the two trained categories may be classified incorrectly.
- The pretrained CNN is frozen in this version; fine-tuning may improve results but requires additional experimentation.
Possible Improvements
- Train for more epochs and compare validation metrics.
- Add data augmentation.
- Fine-tune some MobileNetV2 layers.
- Add precision, recall, F1-score, and a confusion matrix.
- Build a simple web interface for uploading images.
- For actual object detection, use an object-detection model such as SSD or YOLO.
License and Dataset Attribution
This README describes an educational project. Check the dataset's source and license terms before redistributing the dataset or using the project commercially. TensorFlow/Keras and MobileNetV2 have their own licensing terms.
