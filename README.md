# pr2_bimanual_ws

# connect to PR2
## in your local machine, connnect to wifi 'alanLan1' network
''' ssh demos@alan1'''
## password
Ask Others

# setup apriltag
## in root directory of workspace, catkin_make use this
'''catkin_build_isolated'''

## you can put them in your ~/.barshrc
'''
alias sd='source devel/setup.bash'
alias sdd='source devel_isolated/setup.bash'
'''

## launch apriltag in your local machine
'''roslaunch apriltags apriltags.launch'''

## launch openni driver in PR2
'''roslaunch openni_launch openni.launch'''
