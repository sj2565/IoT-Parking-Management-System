# IoT 주차 단속 시스템

## 1. 프로젝트 소개
소방 구역 내 불법 주차 차량 단속에 중점을 두고 이를 위해 센서 및 카메라 모듈을 활용하여 객체 탐지 기술을 적용. <br>
거리 센서와 부저 센서를 활용하여 차량이 감지될 경우, 경고음을 송출하여 운전자에게 주차 금지 구역임을 알림. <br>
경고 방송을 했음에도 불구하고 차량이 계속 주정차 시 카메라 모듈을 통해 차량 감지 후 번호판 인식 및 추출. <br>
추출된 번호판은 데이터베이스에 저장되어 관리자가 웹을 통해 실시간으로 정보 확인 가능. <br>
이후 관리자가 해당 정보를 바탕으로 적절한 조치를 취할 수 있도록 프로젝트 설계. <br>

## 2. 프로젝트 이미지

<img width="450" alt="작품사진" src="https://github.com/user-attachments/assets/635c701f-17a5-46d9-8dc3-339156892f1c" />

## 3. 프로젝트 구조도

<img width="650" alt="구조도" src="https://github.com/user-attachments/assets/01f1446c-12c0-4326-92af-c664e5f505a8" />

## 4. 시퀀스 다이어그램

<img width="750" alt="sequence " src="https://github.com/user-attachments/assets/244fed01-31b5-419c-a0da-5b0ddd205597" />

## 5. 활용된 기술
**언어** : Python, Java, JavaScript, HTML/CSS <br>
**라이브러리** : Numpy, Pandas, Matplotlib, TensorFlow, Pytesseract, OpenCV  <br>
**IDE** : Visual Studio, Python3 IDLE, PyCharm, Android Studio <br>
**프레임워크** : Express, Vue.js <br>
**데이터베이스** : MongoDB <br>
**서버** : Node.js <br>
**머신러닝** : CNN (SSD MobileNet v2 COCO) <br>
**하드웨어** : Raspberry Pi 4 Model B, PiCamera2 <br>

## 6. 프로젝트 실행 이미지
<img width="330" alt="차량탐지" src="https://github.com/user-attachments/assets/95f46333-cc54-45d0-b4d2-0365faab21bb" />&emsp;&emsp;&emsp; 
<img width="400" alt="번호판" src="https://github.com/user-attachments/assets/5c5d67cf-026f-407e-a153-721f8ea30a1f" />
<p>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;차량탐지&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;임의의 번호판 이미지 추출</p><br><br>

<img width="450" alt="실제번호판" src="https://github.com/user-attachments/assets/21472927-0b82-4970-904e-aa1f86a5cd5c" /> <br>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;실제 차량 번호판 번호 추출 <br><br><br>
<img width="500" alt="데이터베이스" src="https://github.com/user-attachments/assets/0b1c9d67-51a4-4021-a07a-95fd7997da09" /> &emsp;&emsp;&emsp;
<img width="400" alt="웹" src="https://github.com/user-attachments/assets/78151b5b-ee4c-402d-b38f-4d10b4f2c286" />
<br> &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;추출된 번호는 데이터베이스로 전달&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;웹을 통해 번호판을 비롯한 다양한 정보 확인

## 7. 설치 및 실행
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
