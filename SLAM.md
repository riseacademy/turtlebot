SLAM은 임의의 공간에서 현재 위치를 추정하여 지도를 그리는 기술이다.

<SLAM 노드 실행>
----------------------

1. Remote PC에서 roscore를 실행한다.

2. Bringup이 TurthleBot3에서 실행되지 않으면 불러오기를 시작한다. (이전에 bringup을 실행했다면 이 단계를 건너뛴다.) ctrl+alt+T키를 통해 Remote PC에서 새 터미널을 열고 IP주소를 통해 Raspberry Pi에 연결한다.

```
$ ssh pi@{IP_ADDRESS_OF_RASPBERRY_PI}
$ roslaunch turtlebot3_bringup turtlebot3_robot.launch
```
3. ctrl+alt+T키를 통해 Remote PC에서 새 터미널을 열고 SLAM node를 설치한다.

```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_slam turtlebot3_slam.launch
```



<Teleoperation Node 실행>
---------------------------

1. 새 터미널을 열고 Remote PC에서 teleoperation node를 실행한다.

```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```

 Control Your TurtleBot3!

 Moving around:
        w
   a    s    d
        x
        
 w/x : increase/decrease linear velocity
 
 a/d : increase/decrease angular velocity
 
 space key, s : force stop
 
 CTRL-C to quit

2. 지도 탐색 및 그리기를 시작한다.
