# DJI Tello drone controller python package

This is a python package which controlls DJI toy drone 'Tello'. The major portion of the source
code was ported from the driver of GOBOT project. For original golang version and protocol in
detail, please refer their blog post at
https://gobot.io/blog/2018/04/20/hello-tello-hacking-drones-with-go

![photo](files/tello-and-gamepad.png)

## How to install
You can install stable version from PyPI.
```
$ pip install tellopy
```
Or install from the source code.
```
$ git clone https://github.com/hanyazou/TelloPy 
$ cd TelloPy
$ python setup.py bdist_wheel
$ pip install dist/tellopy-*.dev*.whl --upgrade
```

## Documents
Please see the API docstring.
```
$ python
>>> import tellopy
>>> help(tellopy)
Help on package tellopy:
...
```

## Examples

You can find basic usage of this package in example code in the examples folder.

### simple_takeoff
This example let Tello take off. Tello will land automatically after a few seconds.

```
$ python -m tellopy.examples.simple_takeoff
```

### video_effect
Filter and display the realtime video stream from Tello.
```
$ pip install av
$ pip install opencv-python
$ pip install image
$ python -m tellopy.examples.video_effect
```
![photo](files/video_effect.jpg)

* pip install av 설치 안되는 경우,    

** 방법1)   
```bash
sudo apt-get install -y python-dev pkg-config

sudo apt-get install -y 
libavformat-dev libavcodec-dev libavdevice-dev 
libavutil-dev libswscale-dev libavresample-dev libavfilter-dev

pip install av
```
Note : ffmpeg을 별도 설치해야 하는 경우, [여기](http://tipsonubuntu.com/2016/11/02/install-ffmpeg-3-2-via-ppa-ubuntu-16-04/) 참고  

** 방법2) 가상환경에서 셋팅 [참고](https://docs.mikeboers.com/pyav/develop/installation.html)
   Note: 2) 방법으로 설치하였을 경우, 미리 셋팅되어있는 가상환경에 설치되므로, tellopy를 해당 가상환경(python3.5)에서 운용해야 함.    
   Note: 파이쎤3.x를 사용하는 경우 ROS와 opencv 연동문제로 다음과 같은 문제 발생   
```bash
ImportError: /opt/ros/kinetic/lib/python2.7/dist-packages/cv2.so: undefined symbol: PyCObject_Type
```
  이 경우, [여기](https://github.com/wsblues/wsDeepDrone/wiki/DeepLearning-%ED%99%98%EA%B2%BD-%EC%85%8B%ED%8C%85#opencv-%EC%84%A4%EC%B9%98) 참조   
 
  
### joystick_and_video
You can use PS3/PS4/XONE joystick to controll Tello.
(see my video https://www.youtube.com/watch?v=MWdNFRdRuj8)
```
$ pip install pygame
$ python -m tellopy.examples.joystick_and_video
```

## for SWARM using built-in wifi and additional usb wifi adapter
아래 참고   
* https://medium.com/@henrymound/adventures-with-dji-ryze-tello-controlling-a-tello-swarm-1bce7d4e045d   
* https://tellopilots.com/threads/tello-drone-swarm.288/
