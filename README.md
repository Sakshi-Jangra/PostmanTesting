# PostmanTesting 🧪
Have you ever created a repository via Git? Many times, I guess. But have you **created a repo via calling HTTP APIs**.


### What is POSTMAN?
Postman is a Google Chrome app for interacting with HTTP APIs. It presents you with **a friendly GUI for constructing requests and reading responses**. It works on the backend, and makes sure that each API is working as intended.<br>
**It is an API client.
Develop, Test(Manual & Automated), Share & Document APIs.**
Postman is the way to streamline the process of API testing.<br> Download Postman for your OS: https://www.postman.com/downloads/

<img src="https://github.com/Sakshi-25/PostmanTesting/blob/main/ScreenShots/POSTMAN.jpg" width="50%"></img><img src="https://miro.medium.com/max/1200/1*tO_SemO2SWDsmN1bzIwmcA.png" width="50%" alt="https://miro.medium.com/max/1200/1*tO_SemO2SWDsmN1bzIwmcA.png" hover="https://miro.medium.com/max/1200/1*tO_SemO2SWDsmN1bzIwmcA.png"></img>

This is my first repository created via POSTMAN with Github API. We will create a Github Access token, use that token to manage our Github Account with Postman, and then Postman will send request to github.com to make a new repository on the account to which the token bolongs to & hurray github responsed with a `Status: 201 Created`.

#### Resources/References: 
Postman on Youtue: https://www.youtube.com/channel/UCocudCGVb3MmhWQ1aoIgUQw <br>
📘 Read about Github APIs: https://docs.github.com/en/free-pro-team@latest/rest <br>
📘 Read about Repositories API version3: https://developer.github.com/v3/ <br>
📘 Read about Repositories API version3 (current version): https://developer.github.com/v3/#current-version

##### Lets start with POSTMAN using Github API. Below are some instructions, follow & you are good to go then.

## Starting with POSTMAN + Github API
- **Step1:** Account on Github -> Settings -> Developer Settings -> Personal Access Tokens -> Generate New Token `copy it`

- **Step 2:** Download & Install Postman. Login with Google or anything and Open it.
  - Create a Workspace
  - Create a Request
  - Go to Envinronment Variable on top-right corner & click on settings(Manage Environment)
      - Add / Creare an environment
      - Name the environment : Github API

          |  variable  |Initial  |Current|
          |----------------|------------------|-----------------|
          |token       |    `Leave it empty`   | `Paste Your github access token here`   |    

    - Update
  - Choose the environment
  - Create a new request
  - Environment Setup is done.

- **Step3:** Now, Make a Request.

  |    POST🔽 	| https://api.github.com/user/repos |
  | ---------------- |------------------|
  | `POST means we are creating a new repo.` | `POST /user/repos` |
  | <details>You can make requests to APIs in Postman. An API request allows you to retrieve data from a data source, or to send data. APIs run on web servers, and expose endpoints to support the operations client applications use to provide their functionality. <br> Each API request uses an HTTP method. The most common methods are  `GET`,  `POST`,  `PATCH`,  `PUT`, and  `DELETE`.<br> -   `GET`  methods retrieve data from an API. <br> -   `POST`  sends new data to an API. <br> -   `PATCH`  and  `PUT`  methods update existing data. <br> -   `DELETE`  removes existing data. <br><p>PUT means to change/update/modify something in existing data on the server and POST means to add new data to the server</p> <br> <img src="https://assets.postman.com/postman-docs/anatomy-of-a-request.png" width="80%"></details> | <details><p>Creates a new repository for the authenticated user.</p> </details> |


- Choose Body
- Select `raw` & `JSON` & paste this example data.
    _Change the repository name and description as per your choice. This Repo will be **Public** as `private = false`_

```json
{
  "name": "Hello-World",
  "description": "This is your first repository",
  "homepage": "https://github.com",
  "private": false,
  "has_issues": true,
  "has_projects": true,
  "has_wiki": true
}
```

- Send
- ```Status: Error 401 Authorization Error(Unauthorised)```
- To Enable Authorization: Go to Authorization -> Type -> Bearer Token (As we have token)-> Put the token as  `{{token}}` (safe way to use token)
- **Send**
- ```Status: OK 201 Created```

### 🎊✨ A repository has been created on your github account🖥


#### Join My Team : <br> https://app.getpostman.com/join-team?invite_code=6fca5c1182d659f6faa3987a216a6c97&ws=8061b583-de7c-48be-b5d4-e2af5f9a6c02
