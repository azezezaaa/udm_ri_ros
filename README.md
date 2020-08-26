# udm_ri_ros
This repo contains all the practicals carried out in RI in Y1S2. Note that each folder represents a separate package. It is recommended to move each package to <catkin workspace>/src/ after retrieving this repo.

## udm_urdf  
#### TP02 - Créer un URDF et le mettre en mouvement
This folder corresponds to "TP02 - Créer un URDF et le mettre en mouvement". Additional information on the tp is available in the PDF file inside the respective folder.
```
cd catkin_ws/src  
git clone https://github.com/azezezaaa/udm_ri_ros.git  
mv udm_ri_ros/udm_urdf/ . && rm -rf udm_ri_ros/  
cd ..  
catkin build  
source devel/setup.bash  
roslaunch udm_urdf visualize_urdf.launch model:='$(find udm_urdf)/urdf/cylinder.urdf'  
roslaunch udm_urdf visualize_urdf.launch model:='$(find udm_urdf)/urdf/main.urdf'  
```

## udm_hand_moveit_config & udm_hand_control
### TP03 - Animer un urdf via Move it  
This folder corresponds to "Animer un urdf via Move it". Additional information can be found in the PDF inside the folder.  
#### Part 1
```
cd catkin_ws/src  
git clone https://github.com/azezezaaa/udm_ri_ros.git  
mv udm_ri_ros/udm_hand_moveit_config/ . && rm -rf udm_ri_ros/  
cd ..  
catkin build  
source devel/setup.bash  
cd catkin_ws/src/udm_hand_moveit_config/launch  
roslaunch udm_hand_moveit_config demo.launch
```
#### Part 2
```
cd catkin_ws/src  
git clone https://github.com/azezezaaa/udm_ri_ros.git  
mv udm_ri_ros/* . && rm -rf udm_ri_ros/  
cd ..  
catkin clean -y && catkin build  
source devel/setup.bash  
roslaunch udm_hand_moveit_config demo.launch  # launch this in the same terminal
```
##### Cinematique directe
```
rosrun udm_hand_control cinematik_direk.py  # launch in terminal 2
# launch in terminal 3 - for info: group names are group_thumb, group_index, group_middle, group_ring, group_pinky
rosservice call /udm_service "joint_goal1:
  data: 0.0
joint_goal2:
  data: 0.0
joint_goal3:
  data: 0.0
group:
  data: 'group_ring'"
```
##### Cinmatique indirecte
```
rosrun udm_hand_control cinematik_indirek.py  # launch in terminal 2
# launch in terminal 3 - for info: group names are group_thumb, group_index, group_middle, group_ring, group_pinky
rosservice call /udm_poseService "orientation:
  data: 1.0
posex:
  data: 0.1
posey:
  data: 0.4
posez:
  data: 0.2
group:
  data: 'group_ring'"
```
