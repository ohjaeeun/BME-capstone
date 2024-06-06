청각 장애인을 위한 Tiny 머신러닝 기반 Warning Glasses (2024 BME CAPSTONE)
====================================================================================================================================================================



프로젝트 목적
-----------------

>저희가 만들고자 하는 주된 이유는 청각 장애인들에게 어플리케이션의 사용 없이 언제나 위험 상황을 감지할 수 있게 하며, 애플워치 등과 같은 관련 제품들과 비교하였을 때 경제적으로 저렴하고 편하게 착용할 수 있는 부분을 고려하였을 때 이와 같은 제품이 적절하다고 생각하였습니다.

프로젝트 도식도 & 설계도
------------------------------------------------
>저희가 진행하려는 프로젝트의 전체적인 흐름을 살펴보면 Part 1에서 Edge Impulse 라는 머신러닝 개발 플랫폼을 활용하여 다음과 같은 순서로 진행하였고,
>
>Part 2에서는 모델이 아두이노에 내장되어 소리 자동 감지 및 진동 모터 작동을 위한 코드 구현을 진행하고 있습니다.

![image](https://github.com/ohjaeeun/BME-capstone/assets/129700005/90a9a5e9-ba88-40b1-bdb0-c73c312e4a1c)


>제품에 대한 예상 결과입니다.

![image](https://github.com/ohjaeeun/BME-capstone/assets/129700005/d11449fc-c7ea-4024-910d-34c3c0192fbf)



Edge Impulse
-----------------------------------------------------------
>저희가 프로젝트에 활용한 머신러닝 플랫폼인 Edge Impulse는 TinyML 기반의 클라우드 플랫폼입니다. 
>신경망 등 다양한 알고리즘을 선택하여 음성을 비롯한 이미지 등의 학습에 사용됩니다. TinyML은 임베디드 하드웨어의 낮은 성능과 저전력 마이크로컨트롤러에서 ML을 구현할 수 있도록 지원하는 기술입니다.
>
>* https://studio.edgeimpulse.com/studio/397181
>
>* 아두이노 ZIP 파일: [ei-ncc-project-1-arduino-1.0.1.zip](https://github.com/user-attachments/files/15619049/ei-ncc-project-1-arduino-1.0.1.zip)
>
>* [Uploading nano_ble33_sense_microphone.ino…]()

아두이노 IDE Setup
--------------------------------------------------
>해당 프로젝트에 사용되는 보드는 arduino nano 33 ble nano sense 이며 보드 내에 센서가 내장되어 보드가 외부 신호를 인식할 수 있습니다.
>먼저 아두이노 IDE를 다운로드하여 설치하고 사용할 라이브러리를 추가합니다.
>스케치 > 라이브러리 포함 > 라이브러리 관리로 이동하여 라이브러리를 추가할 수 있습니다.
>
>* 모델이 저장된 아두이노 라이브러리 :[ei-ncc-project-1-arduino-1.0.1.zip](https://github.com/user-attachments/files/15621906/ei-ncc-project-1-arduino-1.0.1.zip)
>
>
>이후에는 해당 라이브러리를 활용하여 특정 소리를 인식하고 이를 진동 모터의 인식으로 출력하는 코드를 작성합니다. arduino nano 33 ble sense의 특성상 컴파일 속도가 느릴 수 있습니다.

* microphone motor code:
<img width="960" alt="20240606_213147" src="https://github.com/ohjaeeun/BME-capstone/assets/171842597/cd432d08-5763-4748-94b6-9c6149dd0cf1">

>해당 코드로 컴파일 완료 후 특정 소리에 따라 진동모터가 인식되는지 확인할 수 있습니다.

아두이노 도식도
--------------------------------------------------
<img width="260" alt="아두이도 도식도" src="https://github.com/ohjaeeun/BME-capstone/assets/171842597/d84fd103-15cd-449e-8550-0b61560ca641">


>주변소리를 녹음하고 특정 소리(차량 경적소리, 소리지르는 소리 등)가 들리는 경우 안경에 연결한 4번 핀에 아날로그 신호를 주어 진동

