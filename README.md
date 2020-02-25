# CAWR2020
UCL EEE Warehouse Robot - Computer Vision

## Go to catkin_ws folder:
----
1. ROS SETUP
souce devel/setup.bash<br>
roscore<br>

2. CAMERA SETUP
For Openni Camera (Asus):<br>
roslaunch openni_launch openni.launch<br>
For USB WEBCAM (Logitech):<br>
rosrun cv_camera cv_camera_node /cv_camerea/image_raw:=image <br>
FOR ZED2 Camera:<br>
roslaunch zed_wrapped zed2.launch

3. VIEW CAMERA OUTPUT
rosrun image_view image_view image:=/image<br>
rosrun image_view image_view image:=/camera/rgb/image_color<br>

4. BARCODE DETECTOR
rosrun zbar_ros barcode_reader_node image:=/camera/rgb/image_color<br>
rqt_graph<br>
rostopic echo /barcode<br>

Camera Calibration:<br>
rosrun camera_calibration cameracalibrator.py --size 8*6 --suqare 0.108 image:=/image
<br>
TEXT RECOGNITION USING COB_TEXT_DETECTOR
<br>
