# Mid-Term Project: 3D Object Detection

In this project, a deep-learning approach is used to detect vehicles in LiDAR data based on a birds-eye view perspective of the 3D point-cloud. Also, a series of performance measures is used to evaluate the performance of the detection approach.

## Vehicle visibilty examples

*Close front right*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/close_front_right.png)

*Close left top with significant FOV-based occlusion*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/close_left_top_significant_fov_occlusion.png)

*Close right with minimal FOV-based occlusion*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/close_right_minimal_fov_occlusion.png)

*Far rear*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/far_rear.png)

*Far rear with minimal object-based occlusion and edge of LiDAR effective range*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/far_rear_minimal_occlusion_out_of_range.png)

*Far rear with significant object-based occlusion*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/far_rear_significant_object_occlusion.png)

*Mid front line of vehicles*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/mid_front_line_of_vehicles.png)

*Mid front right*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/mid_front_right.png)

*Mid rear left with minimal object-based occlusion*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/mid_rear_left_minimal_object_occlusion.png)

*Mid rear right*
![alt text](https://github.com/GabrielMaguire/sdc-3d-object-detection/blob/main/images/mid_rear_right.png)

## Stable vehicle features

#### Windows
Windows can be observed as the lack of points near the center of the vehicle.
There can be rear, side or front windows.

#### Wheels
Wheels protrude below the main mass off the vehicle.
They are visible from any angle.

#### Rear-view Mirrors
Most prominent from a rear-view where they are small objects that protrude from either side of the vehicle.