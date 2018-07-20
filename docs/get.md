In our first few API requests, we already knew which ORCID iD to use (our own!) and we read/searched public information, which didn't require any permission from the user. In practice, you'll need to gather up iDs for researchers whose ORCID records you want to read, update, or associate with records in your own system AND get permission to take certain actions, like adding information to their ORCID records. In this section, we'll look at a few ways to get authenticated iDs and/or record access permission.

**Authenticated iDs**

ORCID is about disambiguation, it's important that you get the correct iD for each researcher. The best way to do this is to collect **Authenticated ORCID iDs**, which means that each researcher signs into their ORCID account and authorizes your system to obtain their iD. [Learn more about Authenticated iDs](https://orcid.org/blog/2017/02/20/whats-so-special-about-signing)

**Record access permission**

Control over access to data in your ORCID record is one of [ORCID's core princples](https://orcid.org/about/what-is-orcid/principles). While you can read public ORCID data without the record owner's involvement, some API actions require permission:

* Get an Authenticated ORCID iD
* Read non-public data (items with privacy set to 'Trusted parties')
* Add/update record data

##Custom integration

The most customizable way to get Authenticated iDs is by building your own API integration. In this section, we'll walk through the steps that your own custom integration would need to complete in order to get an authenticated iD and record access permission.

**OAuth 2.0**

Getting an Authenticated iD and record access permission from a user involves following [OAuth 2.0](https://oauth.net/2/), an industry-standard protocol for authorization. OAuth allows a user to give a website or application access to account information stored on another site, without giving that site their password.

If you've ever signed into a site using Google or Facebook instead of your credentials for that particular site, you've already used OAuth!

**The OAuth process includes 3 steps:**

1. Create an authorization URL
1. Get an authorization code
2. Exchange the authorization code for an access token

###Get API credentials
API credentials consisting of a **client ID** and a **client secret** are needed in order to get Authenticated iDs and/or user permissions.

To get Authenticated iDs, you can use Public or Member API credentials. To get permission to read non-public information or add/update researchers' ORCID records, you'll need Member API credentials.

For this tutorial, please use your own sandbox API credentials:

To request API credentials, see [Request API credentials](https://orcid.org/content/register-client-application)

(Demo client secret created for this tutorial - do not share API client secrets!)


###Create an authorization URL
To kick off the OAuth process, we'll need to create a special authorization URL that sends users to an ORCID sign-in screen. This URL consists of **Authorization endpoint**, plus **Parameters** that identify your organization and the permissions you want to request.

**Authorization endpoint (Sandbox)**

```https://sandbox.orcid.org/oauth/authorize```


**Parameters**

| Parameter | Description | Example |
| ----------| ----------- | ------- |
|**client_id**| Your Member or Public API client ID (issued by ORCID)<br>To request API credentials, see [Request API credentials](https://orcid.org/content/register-client-application) | ```[APP-*****************]``` |
|**response_type**|  | ```code``` |
|**scope**| API action(s) you want to request permission for, from the list of [ORCID Scopes](https://members.orcid.org/api/oauth/orcid-scopes). | ```/authorize``` <br> ```/activities/update```
|**redirect_uri**| Page on your site that users will see after they complete the authorization process (must be on the list of allowed redirect URIs you specified when requesting your API credentials)  | ```https://developers.google.com/oauthplayground``` |

To request permission to add/update activities (affiliations, funding, works, peer review items), our authorization URL will be:
Enter you own client ID where it says [APP-*****************]
```
https://sandbox.orcid.org/oauth/authorize?client_id=[APP-****************]&response_type=code&scope=/read-limited%20/activities/update%20/person/update&redirect_uri=https://developers.google.com/oauthplayground
```

###Get an authorization Code

1. Copy the below URL, remembering to fill in your own APP details and paste into a new tab.<br>

```
https://sandbox.orcid.org/oauth/authorize?client_id=[APP-****************]&response_type=code&scope=/read-limited%20/activities/update%20/person/update&redirect_uri=https://developers.google.com/oauthplayground
```

2. An ORCID sign-in screen listing the requested permissions will appear; sign into your Sandbox account and click **Authorize**<br>
<img src="../images/04-2_oauth-screen.png" width="400" alt="ORCID OAuth sign-in screen" />
3. After granting permission, you'll be redirected to the Google OAuth Playground. A 6-character code will appear at the end of the redirect URI in the browser address bar (and under the **Step 2** section at left)<br>
<img src="../images/04-2_auth-code-address.png" width="400" alt="ORCID OAuth sign-in screen" /><br><br>
<img src="../images/04-2_auth-code.png" width="400" alt="Browser address bar showing OAuth authorization code" />

###Exchange authorization code for access token & authenticated iD
Once you have an  Authorization Code, you can exchange it for an Access Token and the Authenticated iD of the user who signed in, which you'll need in order to take the API action(s) you requested permission for.

In a real-world situation, this exchange would be done by your system, using a programming language such as  PHP, Java, or Ruby on Rails. For this tutorial, we'll use Google OAuth Playground to simulate a web application.

1. Click the gear icon in the upper right corner to open the **OAuth 2.0 Configuration**<br>
<img src="../images/04-3_google-playground-config.png" width="400" alt="Google OAuth Playground OAuth 2.0 Configuration" />
2. Enter the following settings and click **Close**

| Field | Value |
| ------| ------|
|**OAuth flow**| Server-side |
|**OAuth endpoints**| Custom |
|**Authorization endpoint**| ```https://sandbox.orcid.org/oauth/authorize``` |
|**Token endpoint**| ```https://sandbox.orcid.org/oauth/token``` |
|**Access token location**| Authorization header w/Bearer prefix |
|**OAuth Client ID**| ```[APP-*****************]```<br>(Demo client ID created for this tutorial) |
|**OAuth Client Secret**| ```0000000-0000-0000-0000-000000000000```<br>(Your own client secret created earlier - do not share API client secrets!) |

3. In the **Step 2 Exchange authorization code for tokens** section at left, click **Exchange authorization code for tokens**<br>
<img src="../images/04-3_exchange-code.png" width="400" alt="Google OAuth Playground exchanging authorization code for access token" />
4. Your Access Token and Authenticated iD will appear **Request/Response** section at right.<br>
<img src="../images/04-3_token-response.png" width="600" alt="Google OAuth Playground json response for an access token request" /> <!--update with XML-->

Once you have gone through this process once and you have the token this is all that you need to do further api calls for this ORCID and for these permissions. If you want to make calls for another ORCID or you want to write to a record where before you have only read for example, then you will need to complete the process again and get a new token.
