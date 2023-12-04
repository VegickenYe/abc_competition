# How to run this project 

## Depends
There are few dependes in the project.
- Two hardward:
    1. tianbot_mini
    2. rmtt
- Three softwares:
    1. tianbot_mini 
    2. rmtt_driver
    3. ROS
### [Tianbot_mini](https://github.com/tianbot/tianbot_mini)
tianbot_mini is the self-driven car in the abc_rescue competition
### [RMTT_driver](https://github.com/tianbot/rmtt_ros/tree/main/rmtt_driver)
rmtt is the uav in the competition 

## Prepare 
before running the competition, You need to initialize the environments including :
1. Tianbot_mini slam generate the map, according to [tianbot_mini doc](https://docs.tianbot.com/tianbot_mini/)
2. - [x] change Tianbot_mini params 


## Start(!!!EVERY POINT IN ONE TERMINAL)
Firstly , open two machines and connect them with our PC.
Secondly , open the softwares as following 

1. open the first terminal, run
```bash
roslaunch rmtt_driver rmtt_bringup.launch drone_ip:=xxx.xxx.xxx.xxx(Get from your rmtt_scan_ip.py)
```

2. open the second terminal, run 
```bash
roslauch abc_rescue rmtt_run.launch
```

this will open the rmtt downvision; take off the uav and view different points and the model  
3. open third terminals, input 
```
roslaunch abc_rescue land_search.launch
```
to start the land_search of the tianbot_mini

4. open forth terminals, input 
```
rosrun  abc_rescue send_goal.py
``` 
to run the send_goal, waiting for the model to feed back