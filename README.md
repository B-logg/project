# 자취생들을 위한 식재료 이미지 인식 및 요리 레시피 추천 프로그램
## 서론
코로나로 인한 집콕시대가 시작된 이래 요리와 관련된 유튜브 콘텐츠량의 소비가 폭발적으로 급증하고 있다. 구글 트렌드와 와이즈 랩의 자료를 분석했을 때 유튜브 요리 콘텐츠 소비자는 대부분 20대로 23.3%로 가장 큰 비율을 차지하고 있다.[1] 

![image](https://github.com/user-attachments/assets/a28665b4-5a72-4445-a4b8-b555649f5416)

행정안전부의 자료에 따르면 1인 가구 수는 꾸준히 성장하고 있으며 1인 가구의 약 16%를 유튜브 요리 콘텐츠를 가장 많이 소비하고 있는 20대이다. 이에 자취생 요리 시장 또한 확장될 것으로 기대된다. 
그리고 CHEIL WORLDWIDE의 레포트에 따르면 1인 가구의 음식 관련 검색 키워드 중 레시피 혹은 요리법에 대한 검색 비중이 전체의 40%를 차지한다.[2] 이는 1인 가구원들 역시 집에서 직접 하는 요리에 대한 관심이 높다는 이야기이다.
이를 종합하여 보았을 때 자취생 요리정보에 대한 수요는 증가할 것이며 이에 대응할 수 있는 서비스가 필요할 것으로 보인다. 

## 문제 제기(서두)
자취생 요리정보에 대한 소비가 증가함에 따라 이에 대응하는 수요를 충족시키기 위한 요리 추천 어플 및 자취생 요리와 관련된 영상 콘텐츠가 발전하고 있다. 그러나 기존 요리 추천과 자취생 요리 콘텐츠는 이용자가 요리에 대응하는 재료를 구비해야 요리가 가능하다는 문제점이 있었다. 이는 이용자의 상황에 대한 고려가 이루어지지 못한 것이다. 이로 인하여 발생하는 문제는 이용자가 원하는 요리를 당장 만들 수 없다는 것도 있겠지만 식자재가 남았을 때 보관 혹은 폐기에 대한 문제도 발생할 수 있다.
따라서 본 프로젝트에서는 사용자가 현재 보유하고 있는 식자재 혹은 남은 식자재를 이미지 인식 인공지능을 통하여 파악한 후 레시피를 추천하는 1인 가구 및 자취생 특화 
레시피 검색 프로그램을 제작하고자 한다.

## 문제 범위
본 프로젝트에서는 1인 가구 특히 20대 자취생에 초점을 맞춰 진행할 예정이다.
[그림 1]에서 보이는 것과 같이 1인 가구의 16% 정도를 20대가 차지하고 있고 자취생의 특성상 남는 음식 재료가 상대적으로 많다. 이로 인해 발생하고 있는 1일 1인 음식물 쓰레기 배출량이 약 400g으로 연간 약 2만톤이다.[3] 남은 식자재를 통한 레시피 검색 서비스는 자취생을 대상으로 발생하는 음식물 쓰레기의 양을 줄이는 것을 도울 수 있을 것으로 예상된다. 이는 연간 약 2만톤의 음식물 쓰레기의 감소를 이끌 수 있기에 환경적으로 매우 도움이 될 수 있을 것으로 예상된다. 

## 제안 프로그램
4.1 프로그램 개요
본 프로그램은 이용자가 가지고 있는 재료의 사진을 촬영했을 때 이미지 인식 인공지능을 통해 촬영된 재료를 활용해 만들 수 있는 요리의 레시피들을 추천받을 수 있다. 레시피 추천 방식과 같은 경우 인공지능 구현팀이 작성한 독자적인 알고리즘을 통하여 사진을 통해 인식한 재료들로 만들 수 있는 레시피를 추천 해준 뒤 레시피에 필요한 재료들 중에 현재 보유하고 있지 못한 재료를 따로 보여주는 방식으로 추천이 진행된다. 

4.2 프로그램 내용
본 프로그램을 구성할 때 에디터와 같은 경우에는 Google Colab을 사용하였으며 인공지능 모델과 같은 경우에는 You Look Only Once Version 4 (yolo v4)를 사용했다. 데이터 셋의 학습과 같은 경우에는 Roboflow를 활용하여 진행하였다. 언어는 Python을 사용하였다. 역할 분배와 같은 경우 인공지능 구현팀, 데이터셋 학습팀, 팀 대변 및 보조팀 3팀으로
나누어 진행하였다.

[1단계] Roboflow를 통해 데이터셋 학습

![image](https://github.com/user-attachments/assets/dd8cfd46-c1ec-42f6-b012-d3cac39f2124)

[2단계] Colab을 통한 프로그램 구현

![image](https://github.com/user-attachments/assets/94d9249b-843b-4812-9a90-390df82f2263)

 
4.3 이미지 인공지능 중 Yolo를 사용한 이유
1. object detection 분야에서 가장 많이 알려져 있다. 
2. 1-stage detector 방식을 처음으로 고안해서 실시간으로 객체 검출을 가능하게 한 모델이다. 
3. 이미지 전체를 한번만 본다. 
4. 통합된 모델을 사용하여 간단하게 사용할 수 있다.
5. 기존의 모델 보다 빠른 성능으로 실시간 객체 검출이 가능하다.
즉, 이용자가 촬영하는 사진을 실시간으로 분석하여 피드백을 전달해야 함으로 속도가 가장 빠르며 정확도가 준수한 Yolo 알고리즘을 사용하였다.[4]

4.4 데이터셋 학습에 Roboflow를 사용한 이유
1. 웹으로 구성되어 쉽게 사용이 가능하다.
2. 무료의 데이터셋을 제공한다.
3. 사용자가 가지고 있는 데이터를 업로드하여 커스텀 데이터셋 제작이 가능하다.
4. 데이터셋 증강이 가능하다.
- 데이터셋 증강과정 : 바운딩 박스 처리 된 데이터셋을 generate 시킨 후 export, export한 사진들을 다시 Roboflow에 넣어서 generate하는 과정으로 진행한다.

4.5 구현과정 중 어려웠던 부분
[인공지능 구현팀] - 오류
1번째 : cp오류
class data와 name 파일의 유형을 google docs에서 Names 파일과 Data파일로 변경하여 해결하였다. 이때 Names 파일과 Data파일은 라벨링할때만 생성돼서 따로 파일을 만들 수 없기 때문에 github에서 다운받은 파일을 메모장에서 열어 수정해 사용했다.

![image](https://github.com/user-attachments/assets/99819c85-8a36-47b6-9ab7-7385a41d7288)

2번째: cuda오류
yolov4-custom-cfg파일에 있는 subdivision 파라미터를 64로 변경하여 해결하였다. 

![image](https://github.com/user-attachments/assets/cf1d0a61-7071-4ed2-872e-05b5ca0377db)

3번째: filter 개수 오류 
yolov4-custom-cfg에 있는 파라미터에서 cnn 합성곱층의 filters의 개수를 class 개수에 일치되도록 설정하여 해결하였다.

![image](https://github.com/user-attachments/assets/f09338e1-ea86-4169-b05a-c4ff8207531f)

## 프로그램 구현
■ 음식 재료 학습 과정
1. 커스텀 데이터 제작

![image](https://github.com/user-attachments/assets/9e5d9df8-1892-448c-9069-12fb3d555b13)

2. 학습 진행

![image](https://github.com/user-attachments/assets/c954c610-0570-40e7-9b6e-4f2d6126b14b)

![image](https://github.com/user-attachments/assets/ae18e6fa-2763-4255-91b4-2cebfb0ad5e7)

![image](https://github.com/user-attachments/assets/b706e463-cad2-4a1a-a5ab-55fb636709cf)

![image](https://github.com/user-attachments/assets/7418cba7-7a3f-4e18-94e8-21f909adb39a)

CNN 알고리즘을 이용한 학습을 위해 learning rate, batch, subdivision, epoch을 비롯하여 각각 convolution layer에서의 filter, stride, padding 정보를 custom data에 맞게 yolov4-custom.cfg파일에 작성 및 수정해준다. 설정해준대로 train.txt, test.txt에 담긴 학습데이터 학습한다.

■ 음식 재료 인식 및 처리
1. 음식 재료 인식 및 시각화 과정

![image](https://github.com/user-attachments/assets/6d89ac98-61e6-4c42-bfd3-0f0c38c4634f)

간단한 음식재료 인식 실험을 위해 몇 가지 데이터를 준비하였다.

![image](https://github.com/user-attachments/assets/e494150e-d129-4402-bdde-be96a392c480)

![image](https://github.com/user-attachments/assets/a3572bac-5481-40f1-9cc6-1eafd75d9591)

![image](https://github.com/user-attachments/assets/691fa5dc-7c94-48df-a866-d97a3a85671f)


왼쪽 사진에서의 imShow()함수는 입력된 이미지 데이터를 어떻게 시각화 할 것인지 정의해놓은 함수이다. 이미지의 크기 및 레이블의 시각화에 대한 정보가 담겨있다. 위 사진의 코드를 실행하여 test_images파일 내의 이미지에 대한 인식 및 분류, 신뢰도를 계산하고, imShow함수를 통해 이를 시각화 하였다. 결과는 오른쪽 사진과 같다.

2. 이전 모델의 불편함을 수정한 인식 및 처리 모델
이전의 모델은 일일이 사진들을 하나씩 인식시키면 결과를 하나씩 저장해야한다는 단점이 있다. 그러하여 여러장의 사진을 한번에 처리하는 모델를 제작하였다.

![image](https://github.com/user-attachments/assets/4ecd604c-d354-4267-bc0a-616378800d67)

위 코드는 여러장의 사진 경로를 image_list.txt로 옮겨적고, 이미지 인식 및 분류를 담당하는 코드에 이를 연속적으로 대입하여, 여러개의 결과를 한번에 도출해내는 코드이다. 이는 yolov4에서 판단 결과를 반환한다는 사실을 깨닫고, ‘-out results/result.json’ 명령어를 통해 직접 만든 .json파일에 반환하도록 조작해준 코드이다. 

![image](https://github.com/user-attachments/assets/05c9d477-3a10-4e8b-83d7-910d9d683304)

![image](https://github.com/user-attachments/assets/bbe57804-9060-4e9a-838e-100665e832e5)

사용자가 음식 재료사진을 여러장 찍어 test_images파일에 넣어주고, 실행시킨다면, result.json파일에 위 사진과 같이 인식 및 판단 결과가 이미지 개수만큼 나열된다.

![image](https://github.com/user-attachments/assets/143c11c7-88b6-4645-a2ca-8bc4575a7846)

![image](https://github.com/user-attachments/assets/3d14227a-cd2d-4580-872b-f0f12ed783dd)
  
왼쪽 사진은 result.json파일에 담긴 복잡한 정보 중에서 딱 음식 이미지 인식 및 분류 결과만을 도출해내는 코드이다. 오른쪽 코드는 파이썬 set sequence의 intersection개념을 이용해 직접 고안해낸 음식 추천 알고리즘이다. 왼쪽 코드에서 얻은 이미지 인식 및 분류 결과 데이터를 가지고, 몇 가지 음식에 대한 재료 데이터와 intersection 계산을 통해 현재 상황에서 가장 만들기 편리한 음식 레시피를 추천해주는 알고리즘이다. 

![image](https://github.com/user-attachments/assets/890dc450-a9a9-4398-b814-03ef1f3d3480)

![image](https://github.com/user-attachments/assets/efdd3a51-6841-4fe2-9516-ef68ac493b7b)

 
위 사진과 같이 사용자가 가진 음식 재료들을 인식하여 출력하고, 현재 상황에서 가장 만들기 쉬운 요리를 추천해준다. 만약 부족한 재료가 있다면 부족한 재료를 출력해주고, intersection 계산에서 동등한 값을 가지는 여러 개의 요리가 있다면 전부 출력해주도록 알고리즘을 제작하였다. 또한 output에 대한 가독성을 위해 내가 가진 재료, 메뉴이름, 필요한 재료, 부족한 재료에대한 출력문 색을 다르게 설정해주었다. 음식 추천 알고리즘에서 추천해준 음식들에 대해 사용자에게 선택권을 주어 사용자가 선택한 음식의 재료, 레시피를 최종적으로 출력해주며 알고리즘이 종료된다.

## 결론
본 프로젝트에서는 이미지 인식 인공지능을 활용해 이용자가 보유하고 있는 재료기반으로 요리를 추천해주고 부족한 요리를 추천해주는 프로그램을 구성하였다.
이를 통해 자취생을 포함하는 이용자들의 요리 레시피 탐색에 대한 요구 충족과 레시피 추천 서비스를 제공할 수 있을 것으로 보인다. 그리고 레시피 탐색의 새로운 서비스로 사업화도 충분히 가능할 것으로 예상된다.

### 완성된 프로그램에 대한 설명 영상
유튜브 : https://youtu.be/nJw4ziFREgQ

### 참고문헌
[1] 구글 트랜드 자취 요리 유튜브 검색 통계, 와이즈앱 유튜브 이용시간 추정 통계 
[2] CHEIL WORLDWIDE Report
[3] 환경부, 국내 식품 폐기물 발생 추이
[4] minam.log, 딥러닝 object Detection – Architecture – 1 or 2 stage detector
