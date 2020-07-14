<h1 align="center">
  Sticker Library API
  <br>
</h1>


<h4 align="center">Guide to adding sticker library into your apps and websites.</h4>

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
![GitHub issues](https://img.shields.io/github/issues/stipop-development/Stipop_Sticker_API?style=flat-square)

> Provide a wide range of stickers to users to increase user engagement and retention rate.

Stickers have become almost essential in online communication. Do you have a chat or a messaging feature in your app? Try adding sticker library and let users send great stickers. It has shown that stickers can bring user engagement up by 20% in our case studies. 

## Key Features
* **Sticker Package**
  - 100,000 stickers uploaded by 5,000 global artists around the world. 
  - Customized sticker packs that capture the preferences of your target users, recommended and assorted through Stipop’s millions of user data. 

* **Multi-language Contents**
  - English/Spanish/Hindi/Russian/German/French/Portuguese/Italian/Simplified-Chinese/Traditional-Chinese/Catonese/Japanese/Thai/Indonesian
/Korean

* **Regional Best**
  - Top 100 download list provided in specified langauge speaking countries

* **Weekly Update**
  - All sticker list updated in a weekly basis with new stickers added in automatically

* **Favorites (coming soon)**
  - API to provide list of stickers used the most by a specific end user
  

## Get started :rocket:

To get started you can follow the steps"

1. Read the following 'README' file. If you have any questions you can start an issue or contact us through webmaster@stipop.io.
2. Go to https://stipop.io and sign up for free. Once you sign up you'll get access to a unique API Key for your app in the dashboard.
3. Use the API Key to run test API calls on postman. Now you'll be able to see how things function.
4. Check the UI Kit provided via email and adjust your development roadmap to develop the full feature. 

## Opening Issues :warning:

> Only use the GitHub Issues section if you discovered **issues with the code itself**. Do not mistake the Issues page as a help desk. You can ask for help at [Stipop Support](https://stipop.io/talk-to-expert).  
> For support, please contact <webmaster@stipop.io>.

- Create a [**Issue regarding profile**](https://github.com/stipop-development/Stipop_Sticker_API/issues/new?assignees=&labels=Profile%2C+bug&template=-bug-report----profile.md&title=%5BBUG%5D%5BProfile%5D)
- Create a [**Feature Request**](https://github.com/stipop-development/Stipop_Sticker_API/issues/new?assignees=&labels=enhancement&template=-feature-request-.md&title=%5BFeature+Request%5D)

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
