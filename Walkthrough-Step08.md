# i18n 모델 #
- i18n = internationalization
- 화면의 텍스트를 브라우저의 언어별로 설정하기 위해서 사용
- ResourceModel 모듈을 사용
- i18n 폴더를 UI5 프로젝트의 루트 폴더에 생성하고 해당 폴더 밑에 i18n.properties 파일을 생성하여 작성
	- i18n.properties는 가장 기본 파일
	- 영어인 경우에는 i18n_en.properties
	- 한국어인 경우에는 i18n_ko.properties
	- 브라우저 언어에 해당하는 파일을 우선 반영하며 없는 경우에 i18n.properties 파일의 데이터를 사용한다.

# 실습 #

1) i18n 모델을 사용하기 위해서 ResourceModel 모듈을 import 한다.
 
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/6c27bd79-622b-45d5-8e10-0b2d4d6985b6)


2) i18n 모델을 생성하고 해당 모델을 뷰에서 사용하기 위해서 뷰에 바인딩한다. 모델을 뷰에 바인딩 할 때 이름을 "i18n"으로 지정하면 해당 이름을 가지고 뷰에서 모델의 데이터를 매핑하는데 사용하게 된다. 참고로 뷰에는 여러개의 모델을 바인딩할 수 있으며, 각각의 모델의 바인딩된 이름은 달라야 한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/c257a18b-f14d-48c4-85bd-2c425827abc3)

- this.getView() : this는 현재 컨트롤러를 가르키며 컨트롤러의 함수중 getView()를 통해서 컨트롤러가 매핑되어 있는 뷰 객체를 가져오게 된다.
- bundleName에 "ui5.walkthrough.i18n.i18n"의 의미는 ui5.walkthrough는 webapp 폴더를 가르키며 webapp폴더 밑에 i18n 폴더가 있어야하고 해당 폴더 밑에 i18n.properties 파일을 찾아서 ResourceModel의 데이터로 사용하겠다는 의미이다. 현재는 해당 폴더가 없으므로 다음 Step에서 해당 폴더와 파일을 생성해야 한다.


 3) i18n폴더 및 i18n.properties 파일을 만든다. i18n.properties 파일의 내용은 key=value 형태의 여러개의 항목으로 이루어져 있다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/c7d06ba2-ee85-4ea3-a522-54035b3c278a)

- 뷰 또는 로직에서 key에 해당하는 값을 가지고 value에 해당하는 텍스트를 가지고 와서 사용하게 된다.
- {0}의 의미는 텍스트를 가져오는 i18n 모델의 함수를 호출할 때 파라미터로 배열형태로 ["World"]로 넣어주게 되면 배열의 첫번째 인덱스가 0이어서 {0} 대신에 "World"로 변경이 되어 Hello World가 텍스트로 리턴이 되게 된다.


4) 기존에 메시지를 하드코딩으로 넣었던 것을 i18n 모델을 통해 텍스트를 가져와서 해당 텍스트를 화면에 출력하도록 로직을 수정한다.

<기존로직>

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/45a851af-ffb0-4e4e-a300-722702813829)

<신규로직>

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/7b04bd3b-99bd-42b5-9342-a3d00eda2b5a)

App.controller.js 소스
```
sap.ui.define(
  [
    "sap/ui/core/mvc/Controller",
    "sap/m/MessageToast",
    "sap/ui/model/json/JSONModel",
    "sap/ui/model/resource/ResourceModel",
  ],
  (Controller, MessageToast, JSONModel, ResourceModel) => {
    "use strict";

    return Controller.extend("ui5.walkthrough.controller.App", {
      onInit() {
        // JSON 데이터소스
        const oData = {
          recipient: {
            name: "World",
          },
        };

        const oModel = new JSONModel(oData);
        this.getView().setModel(oModel);

        // i18n 모델을 뷰에 바인딩 한다
        const i18nModel = new ResourceModel({
          bundleName: "ui5.walkthrough.i18n.i18n",
        });
        this.getView().setModel(i18nModel, "i18n");
      },

      onShowHello() {
        // i18n 모델을 가져온다
        const oBundle = this.getView().getModel("i18n").getResourceBundle();
        // 뷰에 할당된 이름없는 모델을 가져와서 해당 모델의 /recipient/name 패스에 해당하는 값을 가져온다
        const sRecipient = this.getView().getModel().getProperty("/recipient/name");
        // i18n 모델에서 helloMsg 키에 해당하는 텍스트에 배열값을 넘겨줘서 텍스트를 가져온다.
        const sMsg = oBundle.getText("helloMsg", [sRecipient]);

        // 메시지를 출력한다
        MessageToast.show(sMsg);
      },
    });
  }
);
```


5) 뷰에서 i18n 모델을 "i18n"의 이름으로 바인딩을 했으므로 해당 모델을 화면 컨트롤의 속성에 아래와 같이 매핑해서 사용할 수 있다. 기본적으로 {모델명>키값}의 형태로 바인딩을 한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/f27ba9fa-88e1-441e-a02e-42b0af1e1487)

위와 같이 입력하면 i18n.properties 파일에서 다음 항목을 찾아서 화면에 출력하게 된다.
![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/2dd214b4-72a6-47c0-a8cb-b5eb453ec8bb)

6) 테스트를 수행한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/f1023b10-6eb7-4e08-bed8-a1c78664958a)

URL을 클릭하면 다음과 같이 화면이 출력되며 표시된 부분이 i18n모델의 텍스트를 이용해서 화면에 출력된 내용이다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/8a19b3d4-2512-4964-9684-1a6f8ec1b6d5)

버튼을 클릭해서 나오는 메시지도 i18n 모델을 이용해서 출력되는 항목이다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/e8c8e448-83d4-4189-a952-db0ae9043ef3)

