# 20240531-10-Step11 : Pages and Panels

  

## **Page** : 전체화면을 나타내는 컨트롤

## **Panel** : 헤더와 컨텐츠 영역을 가지고 있는 컨트롤

  

Page는 다음과 같이 헤더/컨텐츠/푸터등으로 이루어진 전체화면으로 표시되다.

![](https://www.evernote.com/shard/s610/sh/1e53fa5e-aac8-ac73-dba2-8982b70e1a9f/aNn3ru10ravUDVlKNqj4uAtqZvXGW01hOhjZwJdoUK6YSMCyHcByJBxZnQ/res/8e73547a-83bb-a0a8-3341-0cbe7097a5c9)  

  

Panel은 다음과 같이 표시된다.

![](https://www.evernote.com/shard/s610/sh/1e53fa5e-aac8-ac73-dba2-8982b70e1a9f/aNn3ru10ravUDVlKNqj4uAtqZvXGW01hOhjZwJdoUK6YSMCyHcByJBxZnQ/res/376d500a-e20a-9e45-aa67-434b2d340644)  

  

# 실습

### 1\. 모든 컨트롤의 root 태그인 <App>을 다음과 같이 root 뷰에 입력한다.

  

![](https://www.evernote.com/shard/s610/sh/1e53fa5e-aac8-ac73-dba2-8982b70e1a9f/aNn3ru10ravUDVlKNqj4uAtqZvXGW01hOhjZwJdoUK6YSMCyHcByJBxZnQ/res/f57cd41e-a185-ae11-2320-b1e4e36ce195)  

  

### 2\. sap.m.App 모듈은 pages라는 aggregation을 가지고 있으며, 해당 aggregation 안에는 여러개의 Page 컨트롤이 들어갈수 있다. 현재 Page는 하나만 필요하므로 다음과 같이 <Page>컨트롤을 입력한다.

  

![](https://www.evernote.com/shard/s610/sh/1e53fa5e-aac8-ac73-dba2-8982b70e1a9f/aNn3ru10ravUDVlKNqj4uAtqZvXGW01hOhjZwJdoUK6YSMCyHcByJBxZnQ/res/7f8839ff-589d-2a76-9854-6443178db160)  

  

View의 소스를 다음과 같이 수정한다.

  

![](https://www.evernote.com/shard/s610/sh/1e53fa5e-aac8-ac73-dba2-8982b70e1a9f/aNn3ru10ravUDVlKNqj4uAtqZvXGW01hOhjZwJdoUK6YSMCyHcByJBxZnQ/res/e756dff4-a362-d2d8-274c-621efabf42db)  

  

### 3\. Page는 content라는 aggregation을 가지고 있으며 해당 부분에 Panel을 추가한다.

  

![](https://www.evernote.com/shard/s610/sh/1e53fa5e-aac8-ac73-dba2-8982b70e1a9f/aNn3ru10ravUDVlKNqj4uAtqZvXGW01hOhjZwJdoUK6YSMCyHcByJBxZnQ/res/48659282-5907-02ef-2ff5-add07daaeb02)  

  

### 4\. Page에 타이틀을 다음과 같이 추가한다.

  

![](https://www.evernote.com/shard/s610/sh/1e53fa5e-aac8-ac73-dba2-8982b70e1a9f/aNn3ru10ravUDVlKNqj4uAtqZvXGW01hOhjZwJdoUK6YSMCyHcByJBxZnQ/res/dbcee851-c912-b234-61a1-7fff807c7b09)  

  

i18n 파일 (i18n.properties)에 텍스트를 등록한다.

  

![](https://www.evernote.com/shard/s610/sh/1e53fa5e-aac8-ac73-dba2-8982b70e1a9f/aNn3ru10ravUDVlKNqj4uAtqZvXGW01hOhjZwJdoUK6YSMCyHcByJBxZnQ/res/05373aad-559a-91fd-c62e-91391bea775c)  

  

다음과 같이 Page의 제목에 출력이 된다.

  

![](https://www.evernote.com/shard/s610/sh/1e53fa5e-aac8-ac73-dba2-8982b70e1a9f/aNn3ru10ravUDVlKNqj4uAtqZvXGW01hOhjZwJdoUK6YSMCyHcByJBxZnQ/res/3538d85c-7808-5884-9466-c60ea4c14ca0)  

  

### 5\. Panel에 타이틀을 추가하고 i18n 모델에 타이틀의 텍스트를 추가한다.

  

![](https://www.evernote.com/shard/s610/sh/1e53fa5e-aac8-ac73-dba2-8982b70e1a9f/aNn3ru10ravUDVlKNqj4uAtqZvXGW01hOhjZwJdoUK6YSMCyHcByJBxZnQ/res/22412e66-a195-3396-9e05-afce7a28a7c1)![](https://www.evernote.com/shard/s610/sh/1e53fa5e-aac8-ac73-dba2-8982b70e1a9f/aNn3ru10ravUDVlKNqj4uAtqZvXGW01hOhjZwJdoUK6YSMCyHcByJBxZnQ/res/0dd5b0eb-b55d-98e8-3011-5cd9c50065c9)  

  

다음과 같이 Panel의 헤더 텍스트가 출력이 된다.

  

![](https://www.evernote.com/shard/s610/sh/1e53fa5e-aac8-ac73-dba2-8982b70e1a9f/aNn3ru10ravUDVlKNqj4uAtqZvXGW01hOhjZwJdoUK6YSMCyHcByJBxZnQ/res/69475a77-11c1-d452-ca58-b1b8ba67dbee)