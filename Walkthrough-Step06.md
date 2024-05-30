# Walkthrough-Step06 : 모듈

모듈
- 코드를 개별파일로 분리하여 의존성 및 재사용성 향상
- UI5의 모든 라이브러리는 모듈로 작성되어 있으며, 모듈을 사용해서 또다른 모듈을 작성할 수 있다
- 사용자 정의 모듈도 sap.ui.define() 함수를 가지고 만들어서 로직에서 사용 가능

예시) Table 모듈
- ui5.sap.com/resources/sap/m/Table.js 접속
- 다음과 같이 sap.ui.define()을 통해서 모듈을 생성하고 있으며, 다른 모듈을 가져와서 사용하고 있음
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/5fc8d1aa-f67e-4d91-afe1-9e1b4b3d0050)

# 작업방법

1) 화면에 다음과 같이 메시지를 출력하기 위해서 Sample에서 알맞은 Control을 검색한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/aa745942-4dbd-4102-84bb-5e84386d4114)

실행 결과를 확인하고 해당 컨트롤을 사용

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/6f5f255f-d712-4434-a85e-2ec0b7663c10)

2) 로직에서 버튼을 누르면 Message Toast를 화면에 출력하기 위해서 먼저 sap.m.MessageToast 모듈을 import 한다

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/78c0da0e-8759-4025-b22c-45ea3f2233aa)

3) MessageToast를 사용하는 로직을 작성한다. 기존 예제의 팝업을 띄우는 로직을 다음과 MessageToast가 출력되도록 변경한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/aa879d0b-2647-4d5f-a724-59f57a12e3fa)

(관련코드)
```
sap.ui.define(
  ["sap/ui/core/mvc/Controller", "sap/m/MessageToast"],
  (Controller, MessageToast) => {
    "use strict";

    return Controller.extend("ui5.walkthrough.controller.App", {
      onShowHello() {
        MessageToast.show("Hello World");
      },
    });
  }
);
```

4) 테스트를 수행한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/a7a2f42c-344b-4909-87da-ca144d34e873)

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/48fb9350-ad49-49e2-9859-127fa2f3d607)
