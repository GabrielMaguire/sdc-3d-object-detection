# Final Project: 3D Object Detection

In this project we implemented a extended Kalman filter, wrote track management logic, performed data association, and fused data from a lidar and camera sensor to perform robust object tracking. The project was broken down into the four parts described below.

## Overview

#### Extended Kalman Filter

We implemented the extended kalman filter equations in Python using the numpy matrix libraries. The implementation took advantage of pre-built classes for an object track and an object measurement.

*Tracking results with a single object*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/step1_rmse_plot.png)

#### Track Management

A track represents an object and its state and path. In this step a track management class is built to record the state and score for each track. This helps us associate a confidence with each object and mark its state. In the track management class we set the conditions for initializing, deleting, and changing the state of a track.

This was the most challenging section of the project because it required experimenting with the track deletion/change conditions to meet the desired rmse output.

*Tracking results with a single object*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/step2_rmse_plot.png)

#### Data Association

When multiple objects are present in the scene we must have a method of associating new data to a specific track. New measurements are associated with their nearest neighbor, calculated using the MHD equation which accounts for positional uncertainty.

*Tracking results with mutliple objects*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/step3_rmse_plot.png)

#### Camera-Lidar Fusion

Unlike lidar, the camera is a non-linear sensor and input data must be transformed into the measurement space (or vice-versa). In this case, we transform from the vehicle position space into the camera coordinate space for sensor fusion.

*Tracking results with mutliple objects*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/step4_rmse_plot_3.png)

## Benefits of Sensor Fusion

Theoretically, any additional data will help provide a more accurate position estimate by reducing measurement variance. In practice, we see only a small decrease in the rmse tracking values between step 3, using only lidar data, and step 4, using both lidar and camera data.

## Real-Life Challenges

In a scenario with a higher concentration of vehicles, the track association algorithm may have been strained by more tighly packed objects and objects with a less standard trajectory (movement in an unexpected direction). An additional challenge not directly faced in the project is the fusion of multiple camera sensors, either overlapping or adjacent.

## Improvements

For potential improvements I could investigate fine-tuning the various threshold parameters and conditions for initializing, changing, and deleting tracks. This is one of the areas that I noticed significant change in the output results when experimenting.

![](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/my_tracking_results.avi)