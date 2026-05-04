# Who-sThatPokemon
포켓몬 이미지를 넣으면 어떤 포켓몬인지 맞춰드립니다!  
https://colab.research.google.com/drive/1tWTxAm0Rey77W3extIwoUDed08sZsaeH?hl=ko#scrollTo=Vivb-6OT3kXh

--- 

## 실행 방법
1. 위 주소로 들어간다.
2. "여기부터 실행하세요"가 적힌 43번째 블럭을 실행한다.
3. 실행창에서 "접속 비밀번호"의 옆에 있는 IP를 복사하고 출력된 주소로 들어가 복사한 IP를 입력한다.
4. 컨티뉴를 누르고 기다리면 준비 끝
5. 사이트에 이미지 넣는 칸에 원하는 포켓몬 이미지를 넣고 기다리면 자동으로 어떤 포켓몬인지 확인해준다.

## 주의 사항
- 1세대 포켓몬으로만 학습해서 1세대 포켓몬이 아니라면 확인이 어렵습니다.

## 4가지 모델 비교
- 기본 설정 : googlenet | pretrained weight 사용 | 10 epoch만큼 진행 | 트레이닝 데이터와 발리데이션 데이터의 비율 8:2
- 모델 1 : 헤드 부분만 학습하는 모델
- 모델 2 : 헤드와 그 전에 있는 인셉션 블럭을 학습하는 모델
- 모델 3 : 헤드와 그 전에 있는 인셉션 블럭 둘을 학습하는 모델
- 모델 4 : 전체를 학습하는 대신, learning rate가 낮은 모델

  <img width="1590" height="1190" alt="다운로드" src="https://github.com/user-attachments/assets/3b3af544-c054-431e-908c-81f5cc510e6d" />

#### 결론
- 파인 튜닝의 범위가 늘어날 수록, loss나 정확도 등 모든 수치에서 나아지는 경향을 보였다.

## 실제 테스트  
##### 테스트 포켓몬 : Clefairy
<img width="1920" height="1080" alt="스크린샷(271)" src="https://github.com/user-attachments/assets/f1fb2cec-96f3-4fe0-ae5e-fd672217a384" />
<img width="1920" height="1080" alt="스크린샷(270)" src="https://github.com/user-attachments/assets/ae5c87c8-9d2f-4afd-ba10-178b0c7116b0" />
<img width="1920" height="1080" alt="스크린샷(268)" src="https://github.com/user-attachments/assets/f129a109-b162-476e-b04d-bd6fc1e24da4" />
- ditto로 잘못 예측한 경우가 있었다. 추측건대, 얼굴 모양이 ditto(메타몽)과 같아서 그렇게 예측한 것으로 보인다.

##### 테스트 포켓몬 :  Electabuzz
<img width="1920" height="1080" alt="스크린샷(274)" src="https://github.com/user-attachments/assets/c9760c2d-639d-4d37-86aa-9700ed81e868" />
<img width="1920" height="1080" alt="스크린샷(273)" src="https://github.com/user-attachments/assets/893e1646-f6ba-4a81-9e54-fff9f5b5e0c0" />
<img width="1920" height="1080" alt="스크린샷(272)" src="https://github.com/user-attachments/assets/d971e595-71b7-4df7-8dd6-567b1a3ea3be" />
- farfetchd로 잘못 예측한 경우가 있었다. 두 포켓몬의 이마 부분에는 V가 새겨져있는데 이 부분 때문에 착각한 것으로 보인다.

##### 테스트 포켓몬 : Farfetchd
<img width="1920" height="1080" alt="스크린샷(276)" src="https://github.com/user-attachments/assets/78f7409d-91c3-496f-ad7a-53e3a9c4520b" />
<img width="1920" height="1080" alt="스크린샷(277)" src="https://github.com/user-attachments/assets/444304a1-8e2c-4dce-8ea4-569b23932f10" />
