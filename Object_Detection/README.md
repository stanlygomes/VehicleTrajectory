# Object Detection

## Training

If you would like to train the object detection models with the provided or other datasets, the scripts/notebooks to run them have been provided.
Since all of the object detection models are YOLO-based, the dataset will need to be formatted in the YOLO/DarkNet format.

For the purposes of this project, the [Berkeley DeepDrive Dataset (BDD100K)](https://www.vis.xyz/bdd100k/) was used to train the YOLO models.

Here is the directory structure of the "Object_Detection" folder for how a YOLO-formatted BDD100K dataset should be structured to run the scripts:
```
|_ Object_Detection
    |_ datasets
        |_ BDD100K
            |_ images
                { Named images are in these folders below }
                |_ test
                |_ train
                  { Some image names are provided for example }
                  0000f77c-62c2a288.png
                  0000f77c-6257be58.png
                  ...
                |_ val
            |_ labels
                { Named .txt files are in these folders below }
                |_ train
                  0000f77c-62c2a288.txt
                  0000f77c-6257be58.txt
                  ...
                |_ val
            BDD100K.yaml
    |_ yolov5
    |_ YOLO_NAS_BDD100K.ipynb
    |_ requirements.txt
```

### YOLOv8

1. Install the ultralytics python package
```
pip install ultralytics
pip install -r requirements.txt
```
2. Run the following script to train off the BDD100K dataset after it have been converted to YOLO format and imported in the above directory structure:
```
yolo detect train data=./datasets/BDD100K/BDD100K.yaml model=yolov8l.pt epochs=100 imgsz=640
```
With the improvements in usability of YOLOv8, the training runs are saved in a respective "runs" folder.

### YOLOv5

1. Run the following command to ensure all required modules/packages are installed.
```
pip install -r yolov5/requirements.txt
```
2. Run the following command to start training the model with the same prerequisites as YOLOv8:
```
python yolov5/train.py --img 640 --epochs 100 --data datasets/BDD100K/BDD100K.yaml --weights yolov5l.pt
```
The runs should be saved in the yolov5 folder.

### YOLO-NAS

1. Similarly with how YOLOv8 works, the super-gradients python package needs to be installed.
```
pip install super-gradients
```
2. Run through the YOLO_NAS_BDD100K notebook to train, or transfer the code to a .py file and run the script.
