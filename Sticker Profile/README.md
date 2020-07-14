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
  <a href="#11-profile-package-list">1.1 Profile Package List</a> •
  <a href="#12-package-info">1.2 Package Info</a>
  
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

**Base Url:** https://bapi.stipop.io <br>
<br>
The Stipop API is internally implemented based on the RESTful principles. Our API has predictable resource-oriented URLs and is designed to use standard HTTP response codes, authentication, and verbs.

**Authentication:**
<br>
The Stipop API uses API keys to authenticate requests. You can view and manage your API keys in the <a href="https://dashboard.stipop.io/signup" target="_blank">Stipop Dashboard</a>. Your API key carries many privileges, so please keep it secure. Do not share your API key publicly in places like GitHub, blog, and so forth.

Authentication to the API is performed via HTTP Basic Auth. Provide your API key as the basic auth username value. You do not need to provide a password. All API requests must be made over HTTPS. Calls made over plain HTTP will fail. API requests without authentication will also fail.


## 1. Profile Package

### 1.1 Profile Package List

Load sticker profile packages with this API. It contains package general info and category info. Use #1.2 API to load the details of the package. The stickers that are shown in this API have been carefully selected by our content curation team for the best profile images.

* **URL**

  /profile/v0.1/package

* **Method:**

  `GET`
  
*  **Request Headers**

   **Required:**
 
   `apikey=[string]` Issued API Key value from Stipop dashboard.
   

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** <br />
    ```json
    {
      "header": {
          "code": "0000",
          "status": "success",
          "message": "request success"
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
  
### 1.2 Package Info

You can load detail images of the sticker package you loaded by using #1.1 API. Each sticker package has 15~24 stickers. You can apply the same HEX background color to other stickers in the same package OR use your own color sets. 

* **URL**

  /profile/v0.1/package/:packageId

* **Method:**

  `GET`
  
*  **Request Headers**

   **Required:**
 
   `apikey=[string]` Issued API Key value from Stipop dashboard.

* **Request Path Parameters**

  **Required:**
  
  `packageId=[int]`
   

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** <br />
    ```json
    {
      "header": {
          "code": "0000",
          "status": "success",
          "message": "request success"
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
