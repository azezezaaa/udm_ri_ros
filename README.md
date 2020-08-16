# udm_ri_ros
This repo contains all the practicals carried out in RI in Y1S2. Note that each folder represents a separate package. It is recommended to move each package to <catkin workspace>/src/ after retrieving this repo.

## udm_urdf  
#### TP02 - Créer un URDF et le mettre en mouvement
This folder corresponds to "TP02 - Créer un URDF et le mettre en mouvement". Additional information on the tp is available in the PDF file inside the respective folder.
```cd catkin_ws/src  
git clone https://github.com/azezezaaa/udm_ri_ros.git  
mv udm_ri_ros/udm_urdf/ . && rm -rf udm_ri_ros/  
cd ..  
catkin build  
source devel/setup.bash  
roslaunch udm_urdf visualize_urdf.launch model:='$(find udm_urdf)/urdf/cylinder.urdf'  
```
