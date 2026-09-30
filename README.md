# Pedestrian Detection (HOG + SVM)

Detects and counts people in images and video using OpenCV's **Histogram of Oriented Gradients (HOG)** descriptor with the pre-trained linear **SVM** people detector, plus **non-max suppression** to merge overlapping boxes.

## How it works

1. A sliding window moves across the frame at several scales (`detectMultiScale`, stride 4×4, scale 1.03).
2. A HOG feature vector is computed for each window and scored by the linear SVM.
3. Overlapping detections are merged with non-max suppression (overlap threshold 0.65).
4. Each person is boxed and labelled (P1, P2…), and a running **Total Persons** count is drawn on the frame.

## Setup

```bash
git clone https://github.com/Commanderadi/Pedestrian-detection.git
cd Pedestrian-detection
pip install -r requirements.txt   # opencv-contrib-python, numpy, imutils
```

## Run

```bash
python image_op.py    # detect people in the sample image t1.jpg
python video-cam.py   # live detection from your webcam (Esc to quit)
```

## Files

- `Human_Detection.py`: HOG + SVM detector, NMS and drawing (`Detector(frame)`)
- `image_op.py`: runs detection on a single image
- `video-cam.py`: runs detection on a webcam stream
- `IMG/`, `t1.jpg`: sample images

## Stack

Python · OpenCV · NumPy · imutils
