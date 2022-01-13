# 2021년 제10회 세종대학교 SW·AI 해커톤

## 대회 정보
### https://do.sejong.ac.kr/ko/program/all/view/1737

### □ 대회 개요

- 개최일시 : 10월 1일(금) 오전 9:30 ~ 10월 2일(토) 정오 (무박 2일)

- 운영방안 : 코로나 19로 기존의 오프라인 대회를 전 과정 온라인 대회로 전환하여 시행

- 개최장소

&nbsp;&nbsp;&nbsp;&nbsp; - 대회장소 : 온라인 (Cisco WebEx 사용하여 개발상황 실시간 중계)<br>
&nbsp;&nbsp;&nbsp;&nbsp; - 각 조원이 같은 장소에 있어야 할 의무 없음(조원 4명이 각자의 집에서 참여하는 것도 가능)<br>
&nbsp;&nbsp;&nbsp;&nbsp; - 대회본부 : 세종대학교 대양AI센터 콜라보랩<br>

### □ 온라인 참가 방식

 - 스마트폰 카메라, 웹캠 등을 이용하여 10개의 WebEx방 중 자신에게 할당된 주소로 접속하여 상황 중계

 - 심사: 심사를 위한 WebEx방에 접속하여 온라인으로 심사자를 설명

### □ 목적

 - 제한된 시간 내 아이디어 기획부터 직접 개발까지 하는 해커톤을 개최함으로써 학생들의 동기부여 및 성취감 고취

 - 참가자들이 결과물을 다 함께 나누고 즐기는 해커톤 과정을 통해 학생들에게 풍부한 지적 자극과 다른 사람들의 새로운 생각들을 접할 수 있는 기회 제공

 - 숨어있는 개발자 자원 발굴 및 학생들의 개발 역량을 제고하는 기회를 마련 

 - 팀원들과 협업하여 하나의 결과물을 만들어 낼 수 있는 기회를 제공

 - 인공지능 관련 문제 해결을 위한 방안을 제시하고 개발안을 도출함으로써 학생들의 인공지능 기술력 향상을 촉진<br>
 

## 활동

### □ 팀명 : 결혼하면 냉장고
### □ 팀원 : 박지하, 정재욱, 서예진, 심석진
### □ 지정 주제 : 비대면 시험을 위한 AI 시험 감독관<br>
: 비대면 시험 환경에서 실시간으로 입력되는 영상/음성 정보를 관리하고 부정행위와 연계된 이상을 감지하거나 경고 발생 및 녹화 등을 통해서 시험 감독 보조를 도와주는 시스템을 구현
### □ 세부 주제
: 이상 상황(화면에 보이는 얼굴이 하나인지, 두 손이 다 보이는지 등등)을 감지하고 이상 상황이 인지되는 순간마다 경고, 경고가 누적되면 해당 순간의 화면을 캡쳐해 저장하고 감독관에게 전달하는 시스템 개발
### □ 개발 환경 : Jupyter Notebook, PyCharm
### □ 개발 언어 : Python
### □ 사용 기술
#### 1. Face Detection (★)
- Google MediaPipe의 Face Detection 기술 활용
- 검출되는 얼굴의 갯수 파악 가능
- 얼굴 갯수가 하나일 때 : 정상 / 얼굴 갯수가 0개 or 2개 이상 : 부정행위 의심
- 참고 : https://google.github.io/mediapipe/solutions/face_detection

#### 2. Hand Detection (★)
- Google MediaPipe의 Hand Detection 기술 활용
- 검출되는 손의 갯수 파악 가능
- 손 관절의 key point를 추출할 수 있지만, 해당 모델에 필요로 하지 않음
- 손 갯수가 두개일 때 : 정상 / 손 갯수가 1개 이하 or 3개 이상 : 부정행위 의심
- 참고 : https://google.github.io/mediapipe/solutions/hands

#### 3. Head Pose Estimation
- 얼굴이 정면을 바라보고 있는지 판단
- 정면을 바라보고 있는 경우 : 정상 / 정면이 아닌 다른 곳(좌,우,위 등)을 바라보고 있는 경우 : 부정행위 의심
- 제한된 개발 환경(노트북)에서 모든 기술을 다 합쳐 구동하기에는 너무 heavy해지는 문제 발생(frame 끊김, 인식률 저하 등)
- 1차 심사 시에는 적용하였으나, 최종 모델 구현 시 기술 제외시킴<br>
→ 모델이 가벼워지고 정확도 높아짐, 주어진 환경에서 최적의 결과를 내는 것이 중요하다고 판단
- 참고 : https://github.com/park-jiha/Head_Pose_Estimation

#### + Eye Tracking
- 눈동자 시선 추적을 통해 부정행위 여부 판단
- 대회 기간동안 구현하기엔 제한이 있었음(노트북 웹캠으로 받는 frame의 한계, 모델 무거워짐, 코드 이해 부족 등)
- 여러 시도 끝에, 사용하지 않기로 결정

### □ 결과
- 학습 모델에서 이상 상황에 대한 검출 결과 도출
- Flask를 이용한 웹 개발 
- 실제 시험과 유사한 시나리오대로 결과물 완성<br>
(시험 응시생의 인적사항 기입, 공유되는 화면 실시간 송출, 이상 상황이 발생한 순간을 캡쳐해 저장)

### □ 시연 영상
1. 통합<br>
<img src="https://user-images.githubusercontent.com/62232217/148694229-a1f0931e-533f-4f5e-ba26-5cba596e1e91.gif"  width="350" height="600"/>

2. 최종(정상 상황)<br>
<img src="https://user-images.githubusercontent.com/62232217/148694227-9a28b80f-6e22-4517-8142-b15a7a559647.gif"  width="350" height="600"/>

3. 최종(이상 상황)<br>
<img src="https://user-images.githubusercontent.com/62232217/148694226-b83fbbbc-ce2f-4fb1-8836-d800b61392fb.gif"  width="350" height="600"/>

