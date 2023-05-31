1. PC에 Ubuntu를 다운로드 및 설치한다.

2. 원격 PC에 ROS를 설치한다.
ctrl + Alt + T를 통해 터미널을 생성한다.
```
$ sudo apt update
$ sudo apt upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_noetic.sh
$ chmod 755 ./install_ros_noetic.sh 
$ bash ./install_ros_noetic.sh
```
3. 종속 ROS 패키지를 설치한다.
```
$ sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers
  ```
4. TurtleBot3 패키지를 설치한다.
```
$ sudo apt install ros-noetic-dynamixel-sdk
$ sudo apt install ros-noetic-turtlebot3-msgs
$ sudo apt install ros-noetic-turtlebot3
```
5. 네트워크를 구성한다.

5.1. pc를 wifi 장치에 연결하고 $ ifconfig   명령어를 통해 할당된 IP 주소를 찾는다.

5.2. 파일을 열고 $ nano ~/.bashrc  명령어를 통해 ROS IP설정을 업데이트 한다. 

5.3. Alt + / 를 이용하여 커서를 다음줄로 이동한다. 위 터미널 창에서 가져온 IP 주소로 ROS_MASTER_URI와 ROS_HOSTNAME 에서 localhost의 주소로 수정한다. 
5.4. $ source ~/.bashrc명령어를 통해  bashrc의 소스를 지정한다. 

6. TurtleBot3 모델 이름을 설정한다.
```
$ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.ba
```
