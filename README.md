# Utilizing the YOLOv8 Model for Accurate Hand Gesture Recognition with Complex Background

**Download Dataset**
1. Oxford Hand Dataset https://drive.google.com/drive/folders/1W80oYC0ZDG2ABRrW9YhQdsEXvE1gZaIb?usp=sharing

2. Ego Hand Dataset https://vision.soic.indiana.edu/projects/egohands/

**Install and clone the YOLOv8**
1. https://github.com/ChristineDewi/ultralytics-YOLOv8-Hand-Detection
2. https://github.com/ultralytics/ultralytics

**Install**
Pip install the ultralytics package including all requirements in a Python>=3.8 environment with PyTorch>=1.8.

pip install ultralytics

**Prepare the Hand.yaml file train and val data as**
1) directory: path/images/, 2) file: path/images.txt, or 3)

list: [path1/images/, path2/images/]

train: Hand/train/images

val: Hand/valid/images

**# number of classes**
nc: 1

**# class names**
names: [ 'hand']

# **Train**

yolo task=detect mode=train model=yolov8n.pt data=Hand.yaml epochs=50 imgsz=640

yolo task=detect mode=train model=yolov8n.pt data=dataHand.yaml epochs=100 imgsz=640

# **Predict**

yolo task=detect mode=predict  model=runs/detect/train5YoloV8n200epochhand/weights/best.pt data=Hand.yaml imgsz=640  source=data/testhand

yolo task=detect mode=predict model=runs/detect/train3/weights/best.pt data=Hand.yaml imgsz=640 source=data/testhand

yolo task=detect mode=predict model=runs/detect/train5/weights/best.pt data=dataHand.yaml epochs=100 imgsz=640 source=data/video/1a.mp4

# **Validation**

yolo task=detect mode=val model=runs/detect/train5/weights/best.pt data=dataHand.yaml epochs=100 imgsz=640

All Models download automatically from the latest Ultralytics release on first use.

