# Facemask_detector
Tensorflow-based facemask detector
 
 ## Analysis Motivation
Since the Covid-19 pandemic started, face masks have become a norm in life. However, it was a pain in the axx if you want to unlock your iPhone with a face mask on until iOS 14.5
came out (THANK YOU Apple!). I wanted to leverage some fancy deep learning functionalities to develop a facial recognition program specifically for detecting face masks. 

## File Structure
- Python files
  - main.py: file to create label maps
  - update_config.py: update the configuration for the pre-trained model pipeline
  - training_mode.py: train the model and make predictions in real-time

- In the "Tensorflow" folder
  - labellmg: [Labellmg](https://github.com/tzutalin/labelImg) is a graphic annotaiton tool for us to create labels (Mask & Nomask) for the training/testing images
  - models: pre-trained models from the [TensorFlow Model Garden](https://github.com/tensorflow/models) 
  - scripts: a generate_tfrecord.py file to generate TensorFlow record from XML files
  - workspace
    - annotations: label map as well as TensorFlow records for both training and testing set
    - images: training and testing image
    - models: updated MobileNet SSD model with customized configuration
    - pre-trained-models: pretrained models
 
## Techniques and Steps to Run
Packages used:
- [TensorFlow2 Object Detection API](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/install.html)
- TensorFlow
- OpenCV

Steps:
- Download the [Kaggle Face Mask Detection Dataset](https://www.kaggle.com/wobotintelligence/face-mask-detection-dataset)
- Use [Labellmg](https://github.com/tzutalin/labelImg) to create XML files with labels (Mask & Nomask) for all the training and testing images
- Create TensorFlow records for the training and testing set
- Update the pre-trained model (MobileNetSSD V2 FPNLite 320x320) from the [TensorFlow Detection Model Zoo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2_detection_zoo.md)
with custom configuration
- Train the model with the training data
- Use OpenCV to access the web cam for real-time detection


## Credit and Acknowledgement
This project follows the wonderful [tutorial](https://www.youtube.com/watch?v=IOI0o3Cxv9Q&t=2551s) by [Nicholas Renotte](https://www.youtube.com/channel/UCHXa4OpASJEwrHrLeIzw7Yg). 
It also uses pre-trained models from the [TensorFlow Model Garden](https://github.com/tensorflow/models), specifically from the [TensorFlow Model Garden](https://github.com/tensorflow/models), 
along with the image annotation tool [Labellmg](https://github.com/tzutalin/labelImg) and [Kaggle Face Mask Detection Dataset](https://www.kaggle.com/wobotintelligence/face-mask-detection-dataset)

