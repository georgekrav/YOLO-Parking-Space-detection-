# YOLO-Parking-Space-detection-
This project aims to develop a parking space detection system using YOLO (You Only Look Once) technology, which enables real-time object detection. The training model is based on the YOLOv11 architecture and uses a dataset containing images of occupied and available parking spaces.



This repository contains the code and resources for training and testing a YOLO-based neural network to detect parking space availability.

## Project Structure
```
Parking Space/
|-- data/                  # Place your dataset here (train, valid, test folders)
|-- scripts/               # Scripts for training and testing if u create 
|-- runs/                  # Results and saved models (automatically generated)
|-- data.yaml              # Dataset configuration file
|-- README.md              # Project documentation
```

## Prerequisites
1. Python 3.10+
2. Conda environment with the following installed:
   - PyTorch
   - Ultralytics YOLO library
   - OpenCV
3. Graphics card required 
     
### Setting up the Conda Environment
Create and activate the Conda environment:
```bash
conda create -n yolo_env python=3.10 -y
conda activate yolo_env
```
Install the required libraries
Try this command for install all libraries at once to resolve any conflicts:
```bash
conda install -c pytorch -c nvidia -c conda-forge pytorch torchvision pytorch-cuda=11.8 ultralytics
```

## Dataset
The dataset is not included in this repository due to its size. You can download the dataset from the following link:
[Download Dataset](https://universe.roboflow.com/muhammad-syihab-bdynf/parking-space-ipm1b)

### Dataset Structure
The dataset should be organized as follows:
```
data/
|-- train/
|   |-- images/
|   |-- labels/
|-- valid/
|   |-- images/
|   |-- labels/
|-- test/
|   |-- images/
|   |-- labels/
data.yaml
```

## Usage

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/YOLO-Parking-Space.git

cd YOLO-Parking-Space
```

### 2. Download the Dataset
Download the dataset from the link provided above and extract it into the `data/` directory.

### 3. Train the Model
Activate the Conda environment and start training...

Activate conda enviroment: 
```bash
conda activate yolo_env
```
Then start training 
```bash
yolo task=detect mode=train model=yolo11n.pt data="scripts/data.yaml" epochs=100 imgsz=640 batch=16 device=0
```

### 4. Test the Model
To test the model on a video file(you can change conf and see which is the best , at the start set it to 0.5):
```bash
yolo predict model=runs/detect/train/weights/best.pt source=your_video.mp4 conf=0.5
```

## Results
The results of the training and testing will be saved in the `runs/` directory. Check the predictions and model weights there.


