# CAWR2020
UCL EEE Warehouse Robot - Computer Vision

## Go to catkin_ws folder:
----
1. ROS SETUP
souce devel/setup.bash<br>
roscore<br>

2. CAMERA SETUP
-For Openni Camera (Asus):<br>
roslaunch openni_launch openni.launch<br>
-For USB WEBCAM (Logitech):<br>
rosrun cv_camera cv_camera_node /cv_camerea/image_raw:=image <br>
-FOR ZED2 Camera:<br>
roslaunch zed_wrapped zed2.launch

3. VIEW CAMERA OUTPUT (image_pipeline)<br>
-For USB WEBCAM (Logitech):<br>
rosrun image_view image_view image:=/image<br>
-FOR ASUS Camera:<br>
rosrun image_view image_view image:=/camera/rgb/image_color<br>
-FOR ZED2 Camera:<br>
rosrun image_view image_view image:=/zed2/zed_node/rgb_raw/image_raw_color

4. BARCODE DETECTOR (zbar_ros)<br>
rosrun zbar_ros barcode_reader_node image:=/zed2/zed_node/rgb_raw/image_raw_color<br>
rostopic echo /barcode<br>
rqt_graph<br>

5. TEXT DETECTOR (cob_read_text & cob_perception_data)<br>
roslaunch cob_read_text read_text_from_camera.launch (still require adjusting the output)<br>

EXTRA...
Camera Calibration:<br>
rosrun camera_calibration cameracalibrator.py --size 8*6 --suqare 0.108 image:=/image 
<br>

When you try to install a new ROS package:<br>
$ cd ~/catkin_ws/src<br>
$ git clone https://github.com/stereolabs/zed-ros-wrapper.git<br>
$ cd ../<br>
$ rosdep install --from-paths src --ignore-src -r -y<br>
$ catkin_make -DCMAKE_BUILD_TYPE=Release<br>
$ source ./devel/setup.bash<br>
