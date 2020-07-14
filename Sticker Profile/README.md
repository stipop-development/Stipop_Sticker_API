<h1 align="center">
  Stipop
  <br>
</h1>


<h4 align="center">스티커(이모티콘) 스토어 API</h4>

<p align="center">
  <a href="#Intro">Intro</a> •
  <a href="#Key-Features">Key Features</a> •
  <a href="#get-started-rocket">Get Started</a> •
  <a href="#announcements-loudspeaker">Announcements</a> •
  <a href="#opening-issues-warning">Issues</a> •
  <a href="#license">License</a>
	  <br>
  <a href="#1-package">1. Package</a> •
  <a href="#2-donwload-구매-정보">2. Download</a> •
  <a href="#3-analytics">3. Analytics</a> •
  <a href="#4-common">4. Common</a> •
  <a href="#5-my-sticker">5. My Sticker</a> •
  <a href="#6-gift">6. Gift</a>
</p>



## Intro

![Works with Android](https://img.shields.io/badge/Works_with-Android-green?style=flat-square)
![Works with iOS](https://img.shields.io/badge/Works_with-iOS-blue?style=flat-square)
![Works with JavaScript](https://img.shields.io/badge/Works_with-JavaScript-red?style=flat-square)
![GitHub issues](https://img.shields.io/github/issues/stipop-development/Sticker_Store_API_KR?style=flat-square)

> 스티팝 스티커 스토어 API를 통해 서비스에서 새로운 수익을 창출할 수 있습니다.

스티커는 가장 효과적이고 쉬운 감정표현이 가능합니다. 때문에 스티커는 온라인 이용자들에게 필수적인 요소입니다. 카카오톡에서만 사용되던 스티커를 당사 서비스에서 제공해보세요. 쉽고 빠른 설치를 통해 새로운 수익을 창출 할 수 있습니다. 저희는 스티커를 통해 이용자들이 온라인에서 더 효과적으로 커뮤니케이션 할 수 있도록 돕습니다. 

아래 API 문서는 '스티커 스토어' 설치를 위한 문서입니다. 스티커 스토어가 아닌 '일반 스티커' 설치는 <a href="https://github.com/stipop-development/Sticker_Library_API_KR/blob/master/README.md" target="_blank">여기서</a> 확인할 수 있습니다.

## Key Features
* 스티커 인기순위 조회
  - Pricing plan에 따라 20~3,000 패키지 리스트 조회
  - 키워드, 카테고리, 국가, 언어 등의 파라미터를 활용해 세밀한 스티커 리스트 조회 가능
  - 총 25개국 5,000명의 작가가 디자인한 스티커
* 다양한 언어 제공
  - English/Spanish/Hindi/Russian/German/French/Portuguese/Italian/Chinese/Catonese/Japanese/Thai/Indonesian/Korean
* 스티커 구매 정보
  - 쉬운 스티커 판매 모델을 적용한 빠른 개발 및 유료 스티커 수익화
* 스티커 전송 통계
  - 스티커 전송 통계를 통해 보다 세밀한 스티커 추천과 이를 통한 수익 극대화


## Get started :rocket:

아래 API Document를 통해 response 확인 및 서비스에 스티커 스토어를 적용할 수 있습니다. 개발 진행시 발생되는 에러/버그는 이슈에 등록해주시면 24시간 내로 응답됩니다. 새로 추가되는 업데이트는 하단 'Announcement'란에 명시됩니다. 추가 문의는 biz@stipop.io로 해주시기 바랍니다.

v0.1은 스티커 스토어 개발을 위한 기본 기능/스티커를 테스트 해볼 수 있는 버전입니다. 아래는 새로 추가된 기능입니다.<br>
  - 1.3 최근 조회한 스티커 팩<br>
  - 1.4 최근 전송한 스티커<br>
  - 1.5 자주 쓰는 스티커<br>
  - 5.1 위시리스트에 추가/삭제<br>
  - 5.2 위시리스트 조회<br>
  - 5.3 내 스티커 팩 목록 조회<br>
  - 5.4 숨긴 내 스티커 리스트<br>
  - 5.5 내 스티커 숨김 및 해제<br>
  - 6.1 선물 보내기<br>
  - 6.2 선물 받음 확인<br>
  - 6.3 보낸 선물 리스트<br>
  - 6.4 받은 선물 리스트<br>

## Opening Issues :warning:

> 해당 Github Repository에 Bug 혹은 새로운 Feature 제안 Issue를 생성하실 수 있습니다.
> 기타 문의사항은 <biz@stipop.io>에 연락 부탁드립니다.

- [**Bug Report**](https://github.com/stipop-development/Sticker_Store_API_KR/issues/new?template=bug_report.md) 생성하기
- [**Feature Request**](https://github.com/stipop-development/Sticker_Store_API_KR/issues/new?assignees=&labels=&template=feature_request.md) 생성하기

<h4 align="center">
  <br>
</h4>

# API Document

Base Url: https://bapi.stipop.io <br>
<br>
Authentication: 스티팝 스토어 API는 API Key 인증을 통해 사용할 수 있습니다. API Key는 <a href="https://dashboard.stipop.io/signup" target="_blank">dashboard.stipop.io</a>에서 회원가입 후 앱 별로 Unique API Key를 발급 받을 수 있습니다.

API Key는 중요한 정보이니 외부 노출이 되지 않도록 신경써주시기 바랍니다. 특히 Github, blog 등 오픈된 공간에 공유하지 마세요.
Authentication은 HTTP Basic Auth를 통해 실행됩니다. API Key를 Basic Auth Username Value로 제공하시면 됩니다. Password는 제공하지 않으셔도 됩니다.

모든 API Request는 HTTPS를 통해 이뤄져야합니다. HTTP를 통한 Request는 작동하지 않습니다. 또한 Authentication이 되지 않은 Request 또한 작동하지 않습니다.

## 1. Package

### 1.1 Package Ranking List 스티커 팩 인기순위 조회

스티커 팩 인기순위 리스트는 적용된 Pricing Plan에 따라 20개 혹은 200개의 스티커를 불러올 수 있습니다. 스티팝에 업로드 된 모든 스티커는 전 세계 작가들이 제작한 스티커이며 승인되기 위해서는 스티팝 콘텐츠 가이드라인을 통과해야만 합니다. 디폴트로 적용된 인기순위는 스티팝 앱 내 데이터를 통해 정해진 순위이며 개발이 진행됨에 따라 당사 서비스 다운로드를 기준으로 순위가 정해질 수 있습니다. 

* **URL**

  /v0.1/store/package

* **Method:**

  `GET`
  
*  **Request Headers**

   **Required:**
 
   `apikey=[string]` Issued apikey value


* **Request Query Parameters**

  **Required:**
  
  `userId=[string]` 각 개별 사용자를 구분 할 수 있는 고유 값
  
  **Not Required:**
  
  `pageNumber=[int]` 페이지 번호
  
  `language=[string]` 스티커 언어팩 ex) English, Spanish, Korean, German, French, Japanese
  
  `date=[string]` 인기순위 기간  ex) Daily, Weekly, Monthly 미입력시 전체순위
  
  `category=[string]` 스티커 카테고리 x.x의 카테고리 조회후 검색
  
  `animated=[string]` Y: 움직이는 스티커 랭킹조회, N: 스티커 랭킹조회, 파라미터 미입력시 전체조회
  
  `country=[string]` 국가별 랭킹 두자리 국가코드 입력 ex) kr, us, es
  
  `searchText=[string]` 검색어

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** <br />
    ```json
    {
      "header": {
          "code": "0000",
          "status": "success",
          "message": "요청 성공"
      },
      "body": {
          "packageList": [
              {
                  "packageId": 2309,                             //스티커 팩 아이디
                  "packageName": "cada día",                     //스티커 팩 이름
                  "packageImg": "https://img....70AAeHBn4N.png", //스티커 팩 대표 이미지
                  "packageCategory": "Animation/Cartoon,Gag",    //스티커 팩 카테고리
                  "packageKeywords": "bonito,mono,bello,adorable,life,cute,lovely", //스티커 팩 키워드
                  "packageAnimated": "N",                        //움직이는 스티커 여부
                  "isNew": "N",                                  //신규출시 여부
                  "artistName": "pinono",                        //작가 이름
                  "language": "Spanish",                         //언어
                  "isDownload": "Y",                             //구매 여부
		  "isWish": "N"					 //위시 여부
              },
              {
                  "packageId": 2473,
                  "packageName": "¿Cómo estás?",
                  "packageImg": "https://img.....Ggdu7s3J15.gif",
                  "packageCategory": "Phrases,Etc.",
                  "packageKeywords": "¿Cómoestás?,letra",
                  "packageAnimated": "Y",
                  "isNew": "N",
                  "artistName": "annapig",
                  "language": "Spanish",
		  "isDownload": "Y",                             
		  "isWish": "N"					 
              },
              `......`
          ]
      }
    }
    ```
 
* **Error Response:**

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** 
    ```json
    {
      "status": "fail",
      "message": "non exist apikey",
      "code": "9000"
    }
    ```
    OR

  * **Code:** 500 Internal Server error <br />
    **Content:** 
    ```json
    {
       "status" : "fail", 
       "message": "server error", 
       "code":"1000"
    }
    ```

* **Sample Call:**

  ```curl
  curl --location --request GET "https://bapi.stipop.io/store/v0.1/package?userId=xxx&pageNumber=1&country=kr" \ --header "apikey:xxxxxxxxx"
  ```
  


## Announcements :loudspeaker:
Accnouncements regarding major release/update in our products will be shared in the [Annoucements](https://github.com/stipop-development/Stipop_Sticker_API/wiki/Announcements). Please check for new updates so you don't miss our latest releases!


## License

Stipop Sticker API is MIT licensed, as found in the [`LICENSE`](https://github.com/stipop-development/Stipop_Sticker_API/blob/master/LICENSE) file.
