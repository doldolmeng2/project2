# 문제 해결
- 새로운 파일이나 디렉터리 생성 후 작업공간에서 catkin_make 해주어야합니다.
  (project2_ws 디렉터리에서)
- launch파일의 수정이 있을 때도 빌드와 source ./devel/setup.bash 로 환경 변수
  설정해주어야 합니다.
- project_ws/src/launch_file/launch/start.launch 의 ip 값만 바꾼 다음에
  roslaunch launch_file start.launch 로 실행.

- 해당 위치 하위 .py 파일에 실행 권한을 주는 법 
  find . -type f -name "*.py" -exec chmod +x {} \;

- W: GPG error: https://cli.github.com/packages focal InRelease: The following signatures couldn't be verified because the public key is not available:       
  NO_PUBKEY 23F3D4EA75716059
  E: The repository 'https://cli.github.com/packages focal InRelease' is not signed.
  위와 같은 오류 해결은 다음 명령어 치기
  sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 23F3D4EA75716059

- xycar_motor speed값 정리
  1. speed는 1이나 50이나 같은 속도로 가속한다.(최고속도는 모르겠음)
  2. speed 값에 최고 속도가 결정된다. (시작시 가속도도 달라진다)
  3. speed 값은 0.2~1의 값에서 조종한다 (1이나 50이나 같은 가속도로 가속하는걸로 보아 1이상은 다 비슷하고 0.2보다 작으면 안움직임)
  
  # 현재 roslaunch launch_file start.launch 로 실행되는 노드
    - carla_ctl
    - linear_velocity_visualize (현재속도)

# tar.gz 압축
- tar cvzf 파일명.tar.gz <디렉토리 or 파일>

# 도커 명령어

 - 도커 실행 확인 $ sudo systemctl status docker
 - 도커 실행 $ sudo systemctl start docker
수동 주행 동영상 링크
https://youtu.be/zLAAEC7dE_4

# 중요 사항
- 해결한 문제는 여기에 수정해서 쓰기
- 파일 수정은 상관 없지만 파일을 새로 생성해야 하면 꼭 먼저 얘기 한 후 생성.


# 5/30 carla_ctl 룰센서 on off 버전 릴리즈
- deb 파일 다운로드 후 다음 명령어로 설치
sudo dpkg -i /path/to/ros-noetic-carla-ctl_0.0.0-0focal_amd64.deb

# 5/31 TOPIC 이름 변경
- lane_detector 가 발행하는 topic name이 /usb_cam/image_raw -> /lane_detector

# 6/1 
- start.launch 파일 내용 변경했는데 둘 중 하나 실행 가능 한걸로 주석처리 지우고 실행
- IP확인


_rule_sensor_on:= 1/0 룰 센서 on/off 기능 추가
- 새로 다운받은 버전에서 사용 가능
