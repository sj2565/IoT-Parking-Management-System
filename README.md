# IoT 주차 단속 시스템

## 1. 프로젝트 소개
소방 구역 내 불법 주차 차량 단속에 중점을 두고 있습니다. 
이를 위해 센서 및 카메라 모듈을 활용하여 객체 탐지 기술을 적용하였으며, 
차량만을 선별적으로 감지하여 단속하는 시스템을 구축하였습니다. 
감지된 차량의 번호판을 인식한 후, 서버를 통해 단속 차량 정보를 데이터베이스(DB)로 전송하며, 
이후 관리자가 해당 정보를 바탕으로 적절한 조치를 취할 수 있도록 설계되었습니다.

## 2. 프로젝트 이미지

<img width="450" alt="작품사진" src="https://github.com/user-attachments/assets/043153a3-3059-4a3f-bdfa-932dab903b04">

## 3. 프로젝트 회로도

<img width="850" alt="지하철 회로도" src="https://github.com/user-attachments/assets/6d929607-3185-4ba5-b549-eba194ff2b51">

## 4. 활용된 기술
**언어** : C, Python, JavaScript, HTML/CSS <br>
**라이브러리** : Numpy Pandas, Scipy Scikit-learn <br>
**IDE** : Visual Studio, Python3 IDLE, STM32cubeIDE <br>
**프레임워크** : Express <br>
**서버** : Node.js <br>
**머신러닝** : Isolation Forest <br>
**통신** : SPI, UART, WebSocket <br>
**하드웨어** : Raspberry Pi 4 Model B, STM32F411CEU6 <br>

## 5. 프로젝트 실행 이미지
<img width="330" alt="빈좌석" src="https://github.com/user-attachments/assets/2745f2a7-9344-44ce-b4c8-71d6fbafec09" /><p>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;빈좌석 이미지</p>
<img width="330" alt="좌석점유" src="https://github.com/user-attachments/assets/796346cc-e048-4780-8966-c9bb245755ea" />
<img width="330" alt="이상좌석" src="https://github.com/user-attachments/assets/30dfd44f-be11-4f61-9228-3ffd9485f989" /> <br>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;&nbsp;좌석점유 이미지 &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;&nbsp;이상값 좌석 이미지<br><br><br> 
<img width="800" alt="이상값" src="https://github.com/user-attachments/assets/732a0738-6e32-4dbf-b688-ed0406b4a4d9" /> <br> AI 모델 이상값 탐지 : distance가 1213.4로 측정되어 이상값이라 판단.

## 6. 설치 및 실행
**C프로그램 컴파일**
```bash
# 라즈베리파이에서 컴파일 진행
gcc -o SubwaySensor SubwaySensor.c -lwiringPi
```
**Python 라이브러리 설치**
```bash
python3 -m pip install numpy pandas scipy scikit-learn

# pip 설치 안될 시 가상환경을 통해서 설치
python3 -m venv 설정할 이름

# 가상환경 활성화
source 설정할 이름/bin/activate
```

**Node 서버 가동 및 실행**
```bash
node SubwayServer
```
## 7. 향후 개선할 점
+ C -> Node(서버)로 보낼 때 단순 버퍼 형식이 아니라 UART나 TCP/UDP로 활용.
+ AI 모델 평가를 위해 정확도 및 손실함수를 적용.
+ 전송 데이터를 문자열 -> 바이너리로 바꿔서 데이터 크기 감소 및 전송 속도 향상.
-------------------------------------------------------------------------------------
고려해 볼 만한 사항
+ CRC를 추가하여 비트 검사
+ 메모리 관리를 위해 직접 동적 할당
+ Isolation Forest 외에 다른 모델 추가 (Ensemble Learning)
