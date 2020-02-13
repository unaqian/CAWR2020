# CAWR2020
UCL EEE Warehouse Robot - Computer Vision

Go to catkin_ws folder:
souce devel/setup.bash
roscore
rosrun cv_camera cv_camera_node /cv_camerea/image_raw:=image
rosrun image_view image_view image:=/image
rosrun zbar_ros barcode_reader_node
rqt_graph
rostopic echo /barcode
