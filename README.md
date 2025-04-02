# Face Recognition System

## Overview
This project is a real-time facial recognition system built using OpenCV and Python. It detects and recognizes faces using the LBPH (Local Binary Patterns Histogram) algorithm and the Haar Cascade classifier. The system allows users to train a face recognition model, detect faces, and recognize known individuals based on previously stored data.

## Features
- Real-time face detection and recognition
- Uses Haar Cascade classifier for face detection
- LBPH algorithm for face recognition
- Ability to train the model with new faces
- Stores trained model as `trainer.yml`
- Uses `names.json` for mapping recognized faces to names
- Logs system activity for debugging and error handling

## Requirements
### Python Libraries
Ensure you have the required Python libraries installed:
```bash
pip install opencv-python numpy pillow
```

### Project Dependencies
- Python 3.x
- OpenCV
- NumPy
- PIL (Pillow)
- JSON for name mappings
- Logging for debugging

## Project Structure
```
Face-Recognition-System/
│── settings/
│   └── settings.py   # Configuration settings (camera, paths, detection settings)
│── dataset/          # Directory for training images
│── trained_model/
│   └── trainer.yml   # Trained model file
│── haarcascade/
│   └── haarcascade_frontalface_default.xml # Haar cascade classifier file
│── names.json        # JSON file storing face ID-to-name mappings
│── face_taker.py     # Script to capture and save face images
│── face_recognizer.py  # Main face recognition script
│── face_trainer.py   # Training script for face recognition model
│── requirements.txt  # List of required dependencies
│── README.md         # Project documentation
```

## Usage
### 1. Clone the Repository
To use this project, first clone the repository:
```bash
git clone https://github.com/lunawat20/facial_recogntion.git
cd facial_recogntion
```

### 2. Install Dependencies
Run the following command to install the required dependencies:
```bash
pip install -r requirements.txt
```

### 3. Capture Face Images
Before training the model, you need to capture face images using `face_taker.py`.
```bash
python face_taker.py
```
This script will:
- Open the webcam
- Detect faces using the Haar Cascade classifier
- Capture and save face images in the `dataset/` directory

### 4. Train the Model
Once you have collected sufficient face images, train the model:
```bash
python face_trainer.py
```
This script will:
- Load face images from the `dataset/` directory
- Detect faces using the Haar Cascade classifier
- Train the LBPH face recognizer
- Save the trained model as `trainer.yml`

### 5. Run Face Recognition
After training is complete, run the recognition script:
```bash
python face_recognizer.py
```
This script will:
- Initialize the webcam
- Detect faces in real time
- Recognize and display names of identified individuals

## Configuration
All configurable parameters are stored in `settings/settings.py`, including:
- Camera index and resolution
- Path to Haar cascade XML file
- Path to `trainer.yml` model file
- Path to `names.json` mapping file

## Notes
- Ensure the `dataset/` directory contains labeled images before training.
- Each image filename should be in the format: `user-<ID>.jpg`, where `<ID>` is a unique number.
- Press `ESC` to exit the recognition window.

## License
This project is open-source and available for use under the MIT License.

## Repository Link
To contribute or explore further, visit the repository:
[GitHub Repository](https://github.com/lunawat20/facial_recogntion)

