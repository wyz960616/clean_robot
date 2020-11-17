# clean_robot

### 依赖的navigation库
  https://github.com/wyz960616/clean_robot_navigations.git
  将整体的文件放入 /home/用户名/navigation/src/下，并进行catkin_make
  
### 安装本项目
 编译安装本库到 /home/用户名/clean_robot/src/下，并进行catkin_make

### 运行
  注意在每个终端需要source两个工作空间 navigation 和 clean_robot的devel/setup.bash
 
​ roslaunch clean_robot auto_slam.launch为自动探索；roslaunch clean_robot clean_work.launch为弓型清扫。弓型清扫中有一些配置：

​	~/clean_robot/src/config/cleaning_costmap_params.yaml中可以设置弓型的cell，越小弓型越稠密。

​    ~/clean_robot/src/launch/auto_slam.launch中的world是可以改的，0911为自己建立的仿真。

​    ~/clean_robot/src/launch/clean_work.launch中world和maps也是可以改的。 0911.world和hector.yaml对应,clean_room.world和clean_robot.yaml对应。可以自行搭建仿真环境，跑完auto_slam.launch后使用

rosrun map_server map_saver –f 路径保存相应的yaml地图
即可。

​	注意运行clean_work时，跟着轨迹走的path最好改成lines，场景过大，rviz的缓存可能会崩。
