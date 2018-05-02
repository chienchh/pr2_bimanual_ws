# pr2_bimanual_ws

# connect to PR2
### in your local machine, connnect to wifi 'alanLan1' network
``` ssh -X demos@alan1```
### password
Ask Others

# setup apriltag
### in root directory of workspace, catkin_make use this
```catkin_build_isolated```

### you can put them in your ~/.barshrc
```
alias sd='source devel/setup.bash'
alias sdd='source devel_isolated/setup.bash'
```

### launch apriltag in your local machine
```roslaunch apriltags apriltags.launch```

### launch openni driver in PR2
```roslaunch openni_launch openni.launch```

# in virtual machine, make sure to switch the network from NAT to Bridge, NAT is VM connect to Mac wifi so there is one IP address, using Bridge can make VM has its own IP address, which can make PR2 communicate the VM directly




#Moving the Head ON PR2
### Close PR2
```pr2$ robot stop```
```pr2$ robot release```
```pr2$ sudo prw-shutdown```

### wait until it close, push the power button off
### push the power button on, wait until we can connect to the alan wifi

### login pr2
```ssh -X demos@alan1```

### Calibrate the machine
```rosrun pr2_dashboard pr2_dashboard```

### in the Diagnostic column, the third button from the left. Click it and click the reset, then it will start calibrating.

```pr2$ rosrun pr2_controller_manager pr2_controller_manager list```

```pr2$ rosrun pr2_controller_manager pr2_controller_manager start head_traj_controller```

```pr2$ rosnode list head_traj_controller```


Local Machine:
### export local machine ip
```export ROS_IP=10.68.0.192```

### connect to the pr2 network
```pr2-net```
```(export ROS_MASTER_URI=http://alan1:11311)```

### go to ~/pr2_bimanual_ws/src/simple_head/bin
```$ ./point_head```
