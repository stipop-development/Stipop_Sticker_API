<h1 align="center">
  Sticker Profile API
  <br>
</h1>


<h4 align="center">Guide to adding sticker profiles into your apps and websites.</h4>

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

> Get access to unique, fun, and trending profile images that users love.

Sticker Profile API supports a variety of apps from gaming apps, social network apps, image sharing apps and many more. Easily add profile options from our library of 100,000 stickers. Sticker profiles come with default backgrounds which you can use or set your own backgrounds. 

## Key Features
* **Sticker profile from 100,000 sticker images**
  - Stickers are designed by professional sticker artists from 25+ countries
  - 10+ styles are supported to fit your needs

* **Profile category**
  - Supports 5+ categories: Lovely Monster, Animal Friends, Witty Buddy, Doodles, People/Human
  - New categories are added every month with new sticker profiles

* **Background color**
  - Hex code for background colors that match the sticker profile are provided as a default
  - You can use the color code provided or use your own set of colors
  

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

### 1.1 Category Profile Package List 스티커 팩 인기순위 조회

스티커 팩 인기순위 리스트는 적용된 Pricing Plan에 따라 20개 혹은 200개의 스티커를 불러올 수 있습니다. 스티팝에 업로드 된 모든 스티커는 전 세계 작가들이 제작한 스티커이며 승인되기 위해서는 스티팝 콘텐츠 가이드라인을 통과해야만 합니다. 디폴트로 적용된 인기순위는 스티팝 앱 내 데이터를 통해 정해진 순위이며 개발이 진행됨에 따라 당사 서비스 다운로드를 기준으로 순위가 정해질 수 있습니다. 

* **URL**

  /profile/v0.1/package

* **Method:**

  `GET`
  
*  **Request Headers**

   **Required:**
 
   `apikey=[string]` Issued apikey value
   

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
           "profilePackageList": [
            {
                "categoryId": 1,
                "category": "Lovely Monster",
                "packages": [
                    {
                        "packageId": 3887,
                        "packageName": "Tubby Nugget Pack 2",
                        "packageImg": "https://img..._LabUxIW4B4.gif",
                        "packageAnimated": "Y",
                        "backgroundColor": "#F1C4BD"
                    },
                    {
                        "packageId": 3184,
                        "packageName": "Eggbird's moving world",
                        "packageImg": "https://img...cf3o7OuO.gif",
                        "packageAnimated": "Y",
                        "backgroundColor": "#6FBEA9"
                    }
		    .....
                ]
            },
            {
                "categoryId": 2,
                "category": "Animal Friends",
                "packages": [
                    {
                        "packageId": 1054,
                        "packageName": "HELLO CARONG",
                        "packageImg": "https://img.....NG_17.gif",
                        "packageAnimated": "Y",
                        "backgroundColor": "#D696F6"
                    },
                    {
                        "packageId": 4404,
                        "packageName": "a flower-loving penguin",
                        "packageImg": "https://img....O50xG.gif",
                        "packageAnimated": "Y",
                        "backgroundColor": "#799FF5"
                    }
		    .....
                ]
            },
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
  curl --location --request GET "https://bapi.stipop.io/profile/v0.1/package" \ --header "apikey:xxxxxxxxx"
  ```
  
### 1.2 Package Info 스티커 팩 상세

스티커 팩 인기순위 리스트는 적용된 Pricing Plan에 따라 20개 혹은 200개의 스티커를 불러올 수 있습니다. 스티팝에 업로드 된 모든 스티커는 전 세계 작가들이 제작한 스티커이며 승인되기 위해서는 스티팝 콘텐츠 가이드라인을 통과해야만 합니다. 디폴트로 적용된 인기순위는 스티팝 앱 내 데이터를 통해 정해진 순위이며 개발이 진행됨에 따라 당사 서비스 다운로드를 기준으로 순위가 정해질 수 있습니다. 

* **URL**

  /profile/v0.1/package/:packageId

* **Method:**

  `GET`
  
*  **Request Headers**

   **Required:**
 
   `apikey=[string]` Issued apikey value

* **Request Path Parameters**

  **Required:**
  
  `packageId=[int]` 패키지 아이디 값
   

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
	      "package": {
		    "packageId": 1054,
		    "packageName": "HELLO CARONG",
		    "packageImg": "https://img....G_17.gif",
		    "packageAnimated": "Y",
		    "backgroundColor": "#D696F6",
		    "stickers": [
			{
			    "stickerId": 19668,
			    "packageId": 1054,
			    "stickerImg": "https://img....01.gif"
			},
			{
			    "stickerId": 19669,
			    "packageId": 1054,
			    "stickerImg": "https://img...NG_02.gif"
			},
			{
			    "stickerId": 19670,
			    "packageId": 1054,
			    "stickerImg": "https://img...._03.gif"
			},
			......
		     ]
		}
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
  curl --location --request GET "https://bapi.stipop.io/profile/v0.1/package/1054" \ --header "apikey:xxxxxxxxx"
  ```
  


## Announcements :loudspeaker:
Accnouncements regarding major release/update in our products will be shared in the [Annoucements](https://github.com/stipop-development/Stipop_Sticker_API/wiki/Announcements). Please check for new updates so you don't miss our latest releases!


## License

Stipop Sticker API is MIT licensed, as found in the [`LICENSE`](https://github.com/stipop-development/Stipop_Sticker_API/blob/master/LICENSE) file.
