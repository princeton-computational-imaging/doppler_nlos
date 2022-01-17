# Doppler NLOS Code & Datasets

This repository contains code for the paper _Seeing Around Street Corners:
Non-Line-of-Sight Detection and Tracking In-the-Wild Using Doppler Radar_ 
 ([project
webpage](https://www.cs.princeton.edu/~fheide/DopplerNLOS/)).

## Description of Files

The code and data is organized as in the following directory

    ./detection-train-eval.ipynb
        # Jupyter Notebook that includes code for dataloading, training, and
        evaluation with training logs for the detection task.
    ./tracking-train-eval.ipynb
        # Jupyter Notebook that includes code for dataloading, training, and
        evaluation with training logs for the tracking task.
	./training_data
        01-0-bike # scene 1, trajectory 1, bike
            labels # labels for each timestamp
                radar_left_np
                    xxx.txt # The first row is the class name, next three rows are
                    the [x, y] coordinates, [longer dimension, shorter
                    dimension], and the radian angle of the bounding box.
            radar_left_np # input radar data
                xxxx.npy # contains a n x 10 array, where n is the total number
                of radar points, in each row, the first two values are the x,y
                point location in the car coordinate (m), the third is the
                Doppler velocity (m/s), the fourth is the amplitude, the fifth
                is the distance from the sensor (m), the last value is the label
                for object category and should not be used as method input.
            lidar
        01-1-bike # scene 1, trajectory 2, bike
        01-2-pedestrian # scene 1, trajectory 3, pedestrian
        ...
	./validation_data # file structure is the same as training_data

## Data

Please download the train and validation
[data](https://drive.google.com/drive/folders/1ECHM7jvWcnv40bC6E4MN6RQfChtJUy2r?usp=sharing) into the corresponding
directories.

## Environment

The code was tested in a Miniconda environment with Python 3.7 and TensorFlow 2.1.0. Additional package includes NumPy.


## Usage

Please refer to the code and logs in the file detection-train-eval.ipynb and
tracking-train-eval.ipynb for the detection and tracking tasks, respectively.

## Citation
If you find it is useful, please cite
```
@InProceedings{scheiner2019seeing,
author={Scheiner, Nicolas and Kraus, Florian and Wei, Fangyin and Phan, Buu and Mannan, Fahim and Appenrodt, Nils and Ritter, Werner and Dickmann, J{\"u}rgen and Dietmayer, Klaus and Sick, Bernhard and others},
title={Seeing Around Street Corners: Non-Line-of-Sight Detection and Tracking In-the-Wild Using Doppler Radar},
booktitle = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
month = {June},
year = {2020}
}
```
