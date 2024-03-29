# # 1. docker start

→ tmp is for taking datasets 

sudo docker run --name gpu-tree-detection_0.1 -it --privileged \
--env="DISPLAY=0:0" -v=/tmp/.X11-unix:/tmp/.X11-unix --device /dev/bus/usb \
-v=/dev:/dev -v=/tmp:/tmp -w=/home --gpus all \
--network=host gpu-tree-detection/0.1 

## 1.2 docker exec

sudo xhost +local:docker  
sudo docker exec -it 860411ac1b09   /bin/bash

# 2. code Down

```
# tree code download
git clone https://github.com/leggedrobotics/tree_detection.git 

# in your source folder `src`
git clone https://github.com/ANYbotics/grid_map.git 

# install depency files
**sudo rosdep install -yr --from-paths .

# jsk package install
sudo apt install ros-noetic-jsk-visualization** 

```

# 3. Build

→ catkin config is priority

`catkin config -DCMAKE_BUILD_TYPE=RelWithDebInfo`
`catkin build tree_detection_ros`

`catkin build grid_map_rviz_plugin`

# 4. dataset

## 4.1 Dataset download

https://drive.google.com/drive/folders/1m_sRtMN5n6-ShQvnbCfedKIVpoupao5u 

- 4,5 datasets source

https://norlab.ulaval.ca/research/montmorencydataset/ 

4.2 move datasets  

/catkin_ws/src/tree_detection/tree_detection_ros/data
