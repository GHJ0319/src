#Foxglove bridge
ros2 run rosbridge_server rosbridge_websocket
ros2 run rosapi rosapi_node

#Foxglove Web Socket
ros2 launch foxglove_bridge foxglove_bridge_launch.xml port:=8765

#bag
ros2 bag record <topic1> <topic2> 
ros2 bag play <bag>

#maps - https://github.com/danielsnider/MapViz-Tile-Map-Google-Maps-Satellite?tab=readme-ov-file
sudo docker run -p 8080:8080 -d -t -v ~/mapproxy:/mapproxy danielsnider/mapproxy
http://127.0.0.1:8080/demo/
http://localhost:8080/wmts/google_maps/google_grid/{level}/{x}/{y}.png

#gps
ros2 run atgm336h5n3x nmea_node --dev /dev/myserial

#imu
ros2 launch witmotion_ros yahboom10x_launch.py

#navsat node
ros2 launch nav2_gps_waypoint_follower_demo dual_ekf_navsat.launch.py 

#mapviz


#cutting wheel
sudo pigpiod 
ros2 run ros2_pigpio gpio_pwm_writer  --ros-args --param pin:=13
ros2 topic pub --once gpio_pwm_13 std_msgs/msg/Int16 '{data: 64}'


