navigation은 로봇을 한 위치에서 지정된 목적지로 이동시키는 것이다. 이를 위해 주어진 환경의 가구, 사물, 벽 등의 정보를 담고 있는 지도가 필요하다. 

1. 탐색 노드 실행
1.1. 원격 pc에서 ROSCORE가 실행되지 않는 경우 $ roscore 을 실행한다. 
```
$ ssh ubuntu@{IP_ADDRESS_OF_RASPBERRY_PI}
$ export TURTLEBOT3_MODEL=${TB3_MODEL}
$ roslaunch turtlebot3_bringup turtlebot3_robot.launch
$ export TURTLEBOT3_MODEL=waffle_pi
$ roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
```
명령어를 이용하여 내비게이션을 시작한다.

2. 초기 포즈 추정 : 내비게이션에서 중요한 ACML 매개변수를 초기화하기 때문에 내비게이션을 실해하기 전에 초기 포즈 추정을 수행해야 한다. 

2.1. rviz에서 2D Pose Estimate 를 클릭한다.

2.2. 실제 로봇이 있는 지도를 클릭하고 큰 녹색 화살표를 로봇이 향하는 방향으로 드래그한다.

2.3. LDS 센서 데이터가 저장된 지도에 오버레이될 때까지 1단계와 2단계를 반복한다.

2.4. LDS 센서 데이터가 저장된 지도에 오버레이될 때까지 1단계와 2단계를 반복한다.
```
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
2.5. 로봇을 앞뒤로 조금씩 움직여 주변 환경 정보를 수집하고 작은 녹색 화살표로 표시되는 지도에서 TurtleBot3의 예상 위치를 좁힌다.

2.6. 탐색 중에 여러 노드에서 다른 cmd_vel값이 게시되는 것을 방지하기 이해 원격 노드 토미널에 ctrl+C를 입력하여 키보드 원격 작업 노드를 종료한다.

3. 탐색 목표 설정

3.1. rviz에서 2D Nav Goal을 클릭한다.

3.2. 지도를 클릭하여 로봇의 목적지를 설정하고 녹색 화살표(로봇의 목적지를 지정할 수 있는 마커)를 로봇이 향할 방향으로 드래그한다. 

