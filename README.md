# ur5_pic_place
file permissinos-------
cd ~

sudo chown -R user11:user11 ~/mycobot_pick_place_ws

sudo find ~/mycobot_pick_place_ws -type d -exec chmod 755 {} +
sudo find ~/mycobot_pick_place_ws -type f -exec chmod 644 {} +

chmod 755 \
  ~/mycobot_pick_place_ws/src/mycobot_pick_place_sim/scripts/pick_place_sequence.py
  ---------------------------------------------------
  source /opt/ros/jazzy/setup.bash
rosdep install --from-paths src --ignore-src --rosdistro jazzy -r -y

rm -rf build install log
colcon build --symlink-install

source install/setup.bash
ros2 launch mycobot_pick_place_sim pick_place.launch.py
