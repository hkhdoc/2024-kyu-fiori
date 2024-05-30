# manifest.json : 어플리케이션 설정 파일 #

- sap.app
	- 컴포넌트의 네임스페이스 정의 (해당 네임스페이스는 webapp 폴더를 나타낸다)
	- 어플리케이션 제목 및 내역 작성
	- i18n 모델 경로
	- 어플리케이션 버전
- sap.ui : UI 관련 설정
	- UI 기술
	- 사용가능한 기기 설정
- sap.ui5 : UI5 관련 설정
	- rootView : 최초 실행되는 뷰
	- dependencies : UI 라이브러리 설정
	- models : 전역에서 사용할 모델을 설정. i18n, OData 모델등을 설정


manifest.json은 UI5 어플리케이션의 설정 파일이며, UI5 어플리케이션을 실행할 때 필요한 많은 정보를 가지고 있다. 

# 실습 #

1) webapp 폴더 밑에 manifest.json 파일을 다음과 같이 작성한다.

```
{
  "_version": "1.58.0",
  "sap.app": {
    "id": "ui5.walkthrough",
    "i18n": "i18n/i18n.properties",
    "title": "{{appTitle}}",
    "description": "{{appDescription}}",
    "type": "application",
    "applicationVersion": {
      "version": "1.0.0"
    }
  },
  "sap.ui": {
    "technology": "UI5",
    "deviceTypes": {
      "desktop": true,
      "tablet": true,
      "phone": true
    }
  },
  "sap.ui5": {
    "dependencies": {
      "minUI5Version": "1.108.0",
      "libs": {
        "sap.ui.core": {},
        "sap.m": {}
      }
    },
    "models": {
      "i18n": {
        "type": "sap.ui.model.resource.ResourceModel",
        "settings": {
          "bundleName": "ui5.walkthrough.i18n.i18n",
          "supportedLocales": [
            ""
          ],
          "fallbackLocale": ""
        }
      }
    },
    "rootView": {
      "viewName": "ui5.walkthrough.view.App",
      "type": "XML",
      "id": "app"
    },
    "contentDensities": {
      "compact": true,
      "cozy": false
    }
  }
}
```

2) index.html 파일을 수정한다

독립적으로 UI5앱이 시작할 때 필요한 index.html 파일에서도 기본적으로 Component.js파일을 실행하여 앱을 시작하도록 하기 위해서 초기화 로직 설정 부분과 앱의 화면이 출력될 html 파일내의 body 부분을 다음과 같이 수정해 준다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/76d6a5d3-20a7-4b11-9946-bad02a5fd421)


3) 기존 초기화 로직이 들어 있던 index.js 파일은 더이상 필요가 없기 때문에 삭제한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/10987270-f632-4365-b6be-e85f1f62cb5c)


4) Component.js 파일에서 어플리케이션 설정 파일 (manifest.json) 을 읽어와서 초기화 할 수 있도록 로직을 수정한다.


- i18n 모델은 manifest.json 설정에 의해서 생성이 되므로 해당 생성 로직은 제거한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/eab5b5b5-d47c-4291-b240-8fefc8ea9d6e)


5) 테스트를 수행한다.

![image](https://github.com/hkhdoc/2024-kyu-fiori/assets/171245582/f76cae2a-261d-4499-9abc-8ebd9245f7c2)


