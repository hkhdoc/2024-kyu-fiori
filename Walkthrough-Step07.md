# Walkthrough-Step07

# JSON 모델
* **JSON 데이터를 다루는 모델**
* **쉽게 JSON 데이터에서 데이터를 가져오거나 업데이트가 가능하도록 함수를 제공한다.**

⠀
~JSON 데이터 예제~
![](Walkthrough-Step07/image.png)

**API**
![](Walkthrough-Step07/image%202.png)

# 실습

1) JSON 모델을 사용하기 위해서 JSON 컨트롤 모듈을 import 한다.
![](Walkthrough-Step07/image%203.png)

2) JSON데이터는 코드상에 선언, 파일, 원격서비스 리턴데이터 등 여러 데이터소스에서 가져올 수 있지만 JSON 모델의 기능에 대해서 알아보기 위해서 코드상에 다음과 같이 선언한다.
![](Walkthrough-Step07/image%204.png)

3) JSON 모델을 생성하고, 생성시에 JSON 데이터를 모델에 설정한다. 해당 모델은 해당 데이터소스의 JSON 데이터를 다루는 모델이 된다.
![](Walkthrough-Step07/image%205.png)

4) 뷰에 해당 데이터를 출력하기 위해서 모델을 뷰에 바인딩 해야하는데 다음과 같이 생성된 JSON모델을 바인딩 한다.
![](Walkthrough-Step07/image%206.png)
(참고)
* **바인딩** : 모델을 뷰에 출력하기 위해서 모델과 뷰를 연결하는 작업

⠀
5) 모델을 뷰에 바인딩 했으므로 모델의 데이터를 데이터의 경로(path)를 이용해서 사용하고자 하는 컨트롤의 속성에 할당한다. **{[Path]}**로 입력한다.
![](Walkthrough-Step07/image%207.png)
참고로 JSON 모델의 각 항목의 Path는 다음과 같이 표현한다.
![](Walkthrough-Step07/image%208.png)

6) 프로그램을 실행하고 결과값을 확인한다.
![](Walkthrough-Step07/image%209.png)<!-- {"width":492} -->
다음과 같이 바인딩된 JSON 데이터가 출력이 됨을 알 수 있다.
![](Walkthrough-Step07/image%2010.png)