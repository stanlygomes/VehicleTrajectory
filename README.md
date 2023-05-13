# VehicleTrajectory

This project extended on the work done in the research paper ["A POV-based Highway Vehicle Trajectory Dataset and Prediction Architecture"](https://arxiv.org/pdf/2303.06202.pdf).

Since better performing models in object detection have been released, the team researched if results of this paper can be improved on utilizing these models.

## Object Detection

The Object_Detection folder contains the related files for training the object detection models. If you would like to train those models, navigate to that folder on this repository for more detailed instructions with its README.md file.

## Trajectory Prediction

This folder contains the files from each trajectory model's repository. Each folder contains a README.md that informs the user how to train the model. For this projects purposes, [GRIP++](https://github.com/xincoder/GRIP) was trained on the [ApolloScape trajectory dataset](https://github.com/ApolloScapeAuto/dataset-api/blob/master/trajectory_prediction/readme.md) while [PishguVe](https://github.com/tecsar-uncc/pishguve) was trained on the [CHD dataset](https://github.com/TeCSAR-UNCC/Carolinas_Dataset).

## Pipeline

Due to the time constraint of the project, the current pipeline only utilizes the object detection model. In future work, the trajectory model will be implemented to complete the pipeline system for vehicle trajectory prediction. If you would like to see what the current pipeline does, I have repurposed it to count vehicles that pass a line drawn on the screen.
```
python pipeline.py
```

