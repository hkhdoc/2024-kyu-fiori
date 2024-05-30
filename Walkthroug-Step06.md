# Walkthrough-Step06-모듈

모듈
- 코드를 개별파일로 분리하여 의존성 및 재사용성 향상
- UI5의 모든 라이브러리는 모듈로 작성되어 있으며, 모듈을 사용해서 또다른 모듈을 작성할 수 있다
- 사용자 정의 모듈도 sap.ui.define() 함수를 가지고 만들어서 로직에서 사용 가능

예시) Table 모듈
- ui5.sap.com/resources/sap/m/Table.js 접속
- 다음과 같이 sap.ui.define()을 통해서 모듈을 생성하고 있으며, 다른 모듈을 가져와서 사용하고 있음
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/5fc8d1aa-f67e-4d91-afe1-9e1b4b3d0050)

