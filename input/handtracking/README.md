﻿# Pseudo Labeling Hand Bounding Box 
Make hand detected bounding box using pre-trained model. 
- Input: 
  - Image file (.jpeg) 
  - Label file (.txt)
  ```
  # example - img0001.txt
  14
  ```
- Output: Annotation file in YOLOv5 format (.txt) [YOLOv5 Train-Custom-Data](https://github.com/ultralytics/yolov5/wiki/Train-Custom-Data)

Hand Tracking Original Repo is [here](https://github.com/victordibia/handtracking)
```
@article{Dibia2017,
  author = {Victor, Dibia},
  title = {HandTrack: A Library For Prototyping Real-time Hand TrackingInterfaces using Convolutional Neural Networks},
  year = {2017},
  publisher = {GitHub},
  journal = {GitHub repository},
  url = {https://github.com/victordibia/handtracking/tree/master/docs/handtrack.pdf}, 
}
```
## Expected Output (Example)
```
# datasets folder should be next to /yolov5 directory.
├──datasets
|   └──COCO128
|       ├──images
|       |   ├──img0001.jpeg
|       |   ├──img0002.jpeg
|       |   └──     ...
|       |
|       └──labels
|           ├──img0001.txt
|           ├──img0002.txt
|           └──     ...
|       
└──yolov5
```
### Pre-Requisites
You should run one of 
- `../make_full_input.py`
- `../make_input.py`
- `../make_kaggle_input.py`

before making hand annotation.

### 1. Install Requirements
```
pip install -r requirements.txt
```

### 2. Organize Directories
- `datasets` directory should be next to `/yolov5` directory. 
- Make two empty directory
  - `datasets/YOUR_DATASET_NAME/images/`
  - `datasets/YOUR_DATASET_NAME/labels/`

### 3. Run `make_yolo_txt.ipynb`
Before running `make_yolo_txt.ipynb`, 
please refer to expected output directory structure and **change custom var**. 

### 4. Run 
```
python make_annotation.py --datadir /datasets/YOUR_DATASET_NAME
```
