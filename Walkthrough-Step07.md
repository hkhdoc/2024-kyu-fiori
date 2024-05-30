# Walkthrough-Step07 : JSON 모델

### JSON 모델 ###
- JSON 데이터를 다루는 모델
- 쉽게 JSON 데이터에서 데이터를 가져오거나 업데이트가 가능하도록 함수를 제공한다.

### JSON 데이터 예제
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/abde8210-dab9-4442-a2b9-6bcea40cacb7)


### API
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/de3e408e-d1f3-411a-bfc6-1dcdb47975b8)


## 실습

1) JSON 모델을 사용하기 위해서 JSON 컨트롤 모듈을 import 한다.
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/0ed39f42-baea-46f4-a692-5c84fe417b7e)

2) JSON데이터는 코드상에 선언, 파일, 원격서비스 리턴데이터 등 여러 데이터소스에서 가져올 수 있지만 JSON 모델의 기능에 대해서 알아보기 위해서 코드상에 다음과 같이 선언한다.
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/8248fa76-d571-48d3-b3a1-1e9ba34f880f)

3) JSON 모델을 생성하고, 생성시에 JSON 데이터를 모델에 설정한다. 해당 모델은 해당 데이터소스의 JSON 데이터를 다루는 모델이 된다.
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/aa07c1d8-4c07-4ecc-ad29-2c5ff9747ee1)

4) 뷰에 해당 데이터를 출력하기 위해서 모델을 뷰에 바인딩 해야하는데 다음과 같이 생성된 JSON모델을 바인딩 한다.
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/e134f997-dbc1-4e43-a2ed-224b1492cbac)
(참고)
- 바인딩 : 모델을 뷰에 출력하기 위해서 모델과 뷰를 연결하는 작업

5) 모델을 뷰에 바인딩 했으므로 모델의 데이터를 데이터의 경로(path)를 이용해서 사용하고자 하는 컨트롤의 속성에 할당한다. {[Path]}로 입력한다.
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/fdaed8bc-a66c-462f-8155-b2a96b0c25c0)

참고로 JSON 모델의 각 항목의 Path는 다음과 같이 표현한다.
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/56f04f26-2a1d-44db-ab47-aa573d325a67)

6) 프로그램을 실행하고 결과값을 확인한다.
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/3f75c30e-c21c-4249-b23c-833fdc7ab812)

다음과 같이 바인딩된 JSON 데이터가 출력이 됨을 알 수 있다.
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/77ad05ea-991d-43f9-94f5-7ef432974312)
