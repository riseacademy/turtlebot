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

>## 멀티부팅
>https://engpro.tistory.com/430 
1. 노트북에서 윈도우 11과 우분투를 멀티부팅하고자 한다. VMWare에서 PC Setup을 마쳤지만, 가상 환경의 경우 제대로 작동하지 않아 듀얼부팅이 필요하다고 판단되었다.

### 파티션 분할 방법
  파티션 분할 방법에는 두 가지 방법이 있다. MBR(마스터 부트 레코드)와 GPT(GUID 파티션 테이블)이 있다. MBR은 최대 4 개의 파티션만 지원하고, GPT는 MBR을 대체하는 새로운 표준이다. MBR과 다르게 주 파티션 제한이 없다. 아래의 방법은 GPT이다. 윈도우 기본 설정이 GPT이기 때문에 선택하였다. 
  이때, 설치할 보조기억장치(HDD,SDD)는 하나만 있어도 된다. 만약 MBR로 설치한다면 MBR 디스크에서는 주 파티션을 4개 밖에 생성하지 못하기 때문에 주의해서 설정해야 한다. 

2. 준비물
: OS를 설치할 x86 기반 디바이스, 우분투를 설치할 usb, 윈도우를 설치할 usb, 우분투 iso 파일, rufus(software), 윈도우 media creation tool(software)

3. OS iso 파일 다운로드
   1. Ubuntu 22.04.2 LTS
      https://ubuntu.com/download/desktop
   2. Window 11 x 64
      MS사에서 제공하는 미디어 생성 도구를 사용한다.
      
4-1. 설치 USB 만들기(우분투)
   1. rufus를 사용해서 UEFI 모드로 우분투 설치 USB로 만든다.
      ![image](https://github.com/riseacademy/turtlebot/assets/134995480/4ca7cb3c-9ba4-49db-8e44-d6beb28e3b32)
  2. 파티션 구성은 GPT, 대상 시스템은 UEFI로 설정해준다.
4-2. 설치 USB 만들기(윈도우)
  1. MS에서 제공하는 미디어 생성 도구를 사용해서 UEFI 모드로 USB를 윈도우 설치 USB로 만든다.

5. 우분투 설치
   : ubuntu grub이 기준이 되어 부팅 시 OS를 선택하게 된다. 윈도우 부트 매니저가 먼저 실행되게 되면 우분투가 인식되지 않는 것 같으므로 우분투 부트 매니저가 먼저 실행되어야 한다. 바이오스에서 부트 매니저 순서를 변경 가능하나, 어떤 바이오스에서 지원되지 않을 수 있으므로 가급적 우분투를 먼저 설치한다.
   (1) 설치 USB를 컴퓨터 본체에 삽입한다.
   (2) pc를 부팅하고 F7 키를 누른다. 원하는 장치로 부팅을 하게 된다.
   (3) 설치 usb를 선택한다.
   (4) 우분투를 설치한다. 이때 설치 형식에서 기타를 눌러 파티션을 직접 설정한다.
   (5) 파티션 옵션 설정
   
