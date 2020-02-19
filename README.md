# CAWR2020
UCL EEE Warehouse Robot - Computer Vision

Go to catkin_ws folder:
----
souce devel/setup.bash<br>
roscore<br>
roslaunch openni_launch openni.launch
rosrun cv_camera cv_camera_node /cv_camerea/image_raw:=image<br>
rosrun image_view image_view image:=/image<br>
rosrun zbar_ros barcode_reader_node<br>
rqt_graph<br>
rostopic echo /barcode<br>

Camera Calibration:<br>
rosrun camera_calibration cameracalibrator.py --size 8*6 --suqare 0.108 image:=/image
