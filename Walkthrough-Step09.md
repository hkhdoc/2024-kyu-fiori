# Component.js

- Fiori 런치패드에서는 이미 런치패드 프로그램을 통해서 화면에 html이 출력된 상태라서, 특정 영역에 여러 UI5 어플리케이션을 번갈아 가면서 출력하는 것은 UI5 어플리케이션의 index.html을 가지고 시작할 수 없다.
- UI5에서는 sap/ui/core/UIComponent 라이브러리를 이용해서 만든 Component.js 파일으로 UI5 어플리케이션을 시작해서 웹페이지의 특정 영역을 해당 결과값을 가지고 출력하도록 프로그래밍이 가능하다.
- 해당 파일은 webapp 폴더 바로 밑에 위치시켜야 한다.


즉, UI5어플리케이션을 실행하는 방법은 다음의 두가지 방법이 존재한다. 

- index.html을 통해서 독립적인 App을 실행
- Component.js파일로 부터 실행하여 다른 App안에 종속적으로 실행


Componet.js 파일에는 다음의 로직이 포함되어 있다.

- UI5앱의 기본 설정
- 가장 최초 실행이 되는 rootView설정
- 앱 전역에서 사용할 모델 정의


# 실습

1) 먼저 webapp 폴더 밑에 Component.js 파일을 생성하고 기본적으로 sap/ui/core/UIComponent를 확장하여 초기화 하는 기본 로직을 작성한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/a2c80007-1939-4711-951d-754839ff8709)


2) Component의 ID를 설정한다. [Namespace].Component 형태로 이름을 지정한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/b3179224-9a7d-4bad-8136-ea545c6402e3)


3) Component.js에는 위의 init() 초기화 함수와 metadata 설정 영역 두가지로 이루어져 있으며, metadata에 UI5 앱이 실행할 때 가장 먼저 생성이 되는 Root View를 설정한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/6909bb80-2cb4-480a-93b1-2be080d9fb10)


4) Component.js의 초기화 함수인 init에 뷰에서 사용할 JSON 모델과 i18n모델을 생성해서 컴포넌트에 바인딩한다. 컴포넌트에 바인딩하게 되면 모든 뷰와 컨트롤러에서 해당 모델을 사용할 수 있다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/1411ce77-ca63-4a03-97f0-541d8d268783)


5) 기존에 컨트롤러 App.controller.js의 init() 함수에 작성했던 Model 생성 로직을 삭제한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/9581c1cb-1443-49f2-a47e-79ba0d2db952)

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/61783660-adca-48c5-9383-172276a8207e)


6) 아직까지는 Fiori 런치패드등에서 APP을 실행하는게 아니라 index.html을 통해서 standalone 방식으로 실행해야 하므로 기존에 초기 화면을 만드는 로직을 Component를 가지고 화면을 만드는 로직으로 수정한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/4219a716-4291-4050-aab2-45cf1f61c872)

- 화면에 출력하기 위해서 ComponentContainer를 가지고 Component 설정하는 로직이며, name의 ui5.walkthrough는 webapp 폴더를 의미하므로, 해당 폴더 밑에 Component.js 파일을 가지고 실행을 해라라는 의미
- Fiori 런치패드에서는 ComponentContainer의 역할을 런치패드가 수행하게 된다


7) 테스트를 수행한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/6c817931-6c99-4c30-b3a9-418011eec72e)

다음과 같이 기존 실습과 동일한 화면이 출력이 된다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/23ba17fd-f596-41c1-934e-e78fb2c49db3)


