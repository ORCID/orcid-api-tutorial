#Explore the ORCID registry
##Create an ORCID iD
<img width="194" height="336" src="http://alainna.org/orcid/clip_image002.gif" align="right" hspace="12" vspace="12" alt="Screen Shot: ORCID registration screen at https://sandbox.orcid.org/register" /><a name="2.1"></a>
In order to try out API calls, such as a reading a record and adding information to it, you will also  need to create a test ORCID record. This can be done through the  user interface, much like in the live ORCID registry.

  *Open a web browser and navigate to <a href="https://sandbox.orcid.org/signin" target="_blank">https://sandbox.orcid.org/signin</a><br />&nbsp;
  *Click **Register for an ORCID iD**.<br />&nbsp;
  *Complete the form with a name, email, and password. You will need to remember this information for future steps.
**<em>IMPORTANT! </em>**<em>Don&rsquo;t use a real email address! Instead, make up an address  ending in @mailinator.com (use any prefix, e.g. sgarcia@mailinator.com).</em>
  *Click the **I consent…** checkbox and click **Register**.<br />&nbsp;
  *After completing the registration process, you will be  taken to your new testing ORCID record. Make note of the 16-digit ORCID iD for this record – you will need this in order to make API calls later during the workshop.<br />
    <img src="http://alainna.org/orcid/clip_image004.jpg" alt="Screen Shot: Top section of the my-orcid page, showing the ORCID iD in the left column under the name at https://sandbox.orcid.org/my-orcid" width="645" height="107" border="0" /><br />&nbsp;


##Explore the ORCID record
In this section we will learn about the parts of an ORCID record, and explore ORCID's provenance model.

  *Using the interface, add a sentence or two to serve as the biography for your test record. The biography section is located at the top of the right column, and the edit button is the pencil icon in the upper right corner of this section, next to the visibility selector.<br />&nbsp;
  *In the **Employment** section, click **Add employment** > **Add manually** to add employment information.<br />&nbsp;
  *After saving your employment information, notice the information on the bottom of the "card" you just created. There is a Source field (that matches your name because you added this information) and the date that you created this addition to your record. This provenance information is recorded for all infomration added to an ORCID record.<br />&nbsp;
  *In the main menu at the top of the screen, click on the **Account settings** link to display your account preferences. Notice each section to see what iD holders can control with their ORCID accounts.<br />&nbsp;
  *In the main menu at the top of the screen, click on the **Developer tools** link. In this section a user may obtain credentials to access the public API. Note that this API is different from the member API that we will be discussing today.


##Connect your new iD with your IdP
Since there are over 2.5 million ORCID iDs, many people already have an ORCID iD when they link to their IdP. To experience this proces, we will sign out of your test record and start from the prospective of someone who has an iD, and notices that they can sign in with IdP credentials.

  *Sign out of the ORCID record you just created by clicking the **Sign out** button in the upper right corner. <em>Alternatively, you can navigate to the URL: <a href="https://sandbox.orcid.org/signout" target="_blank">https://sandbox.orcid.org/signout</a>.</em><br />&nbsp;
  *On the Sign in page (<a href="https://sandbox.orcid.org/signin" target="_blank">https://sandbox.orcid.org/signin</a>), choose **Sign in using your Institutional Account** to see the list of supported eduGAIN institutions.<br />&nbsp;
  *Enter your organization's name in the box, or choose to pick it from the list. If you do not have credentials at an eduGAIN-included institution, you may use **United ID** for this example. <em>(you will need 2-factor authentication to use United ID.)</em><br />&nbsp;
  *After signing into your institution, you will be asked to finish linking the accounts by providing your ORICD sign in credentials. Type in the email address / ORCID iD and Password that you created in the previous step. Click **Sign into ORCID** to finish linking your accounts.<br />&nbsp;
  *On the my-orcid page that appears, notice an orange alert box confirming that the accounts are linked, and suggesting that you connect to the university's account. This is an example, of the cross linking that we will be exploring further today. We will ignore this message for now.

#ABOUT THE ORCID APIs
##ORCID API types &amp; features
ORCID offers several APIs (Application Programming Interfaces) that allow your systems to connect to the  ORCID registry, including reading from and writing to ORCID records. Some API  functions are freely available to anyone; others are available to organizations  that financially support ORCID with an annual membership subscription.

| API&nbsp;Version   | Access | Features |
| -------------- | ------ | --- |
**Public&nbsp;API** | Freely available to anyone | **Authenticate:** Obtain a user&rsquo;s authenticated ORCID iD<br> **Read (Public):** Search/retrieve public data<br> **Create:** Create new ORCID records on demand
**Member&nbsp;API** | Available to organizations that support ORCID with an annual membership subscription<br>*(Sandbox Member API freely available to all for testing)* | All Public API features, plus:<br> **Read (Limited):** Search/retrieve public data<br> **Update:** Post new items to a record (affiliations, works, etc.) or edit items that you added previously

##Sandbox test environment
In addition to the  production Registry and APIs, ORCID also offers a testing environment, the ORCID Sandbox, which we will be using for this boot camp. The Sandbox is open  to all users and provides a place to develop and test applications without affecting data in the live ORCID registry.
 The Sandbox includes:

* <a href="https://sandbox.orcid.org/signin" target="_blank">Sandbox Registry</a>: Simulates the ORCID Registry <br />&nbsp;
* <a href="https://members.orcid.org/api/introduction-orcid-member-api">Sandbox Member API</a>: Simulates the Member API<br />&nbsp;
* <a href="https://members.orcid.org/api/introduction-orcid-public-api">Sandbox Public API</a>: Simulates the Public API

The sandbox behaves the same  way as the production ORCID Registry with a few exceptions: 

* Search &amp; Link tools do not function.<br />&nbsp;
* To avoid unintentional spamming, the Sandbox sends  emails only to @mailinator.com addresses. <a href="https://mailinator.com/" target="_blank">Mailinator.com</a> is an inbox testing service  that is free and requires no registration. To receive emails from the Sandbox,  use an @mailinator.com email address when creating Sandbox record(s).<br />&nbsp;
* Links in the top menu bar (For Researchers, For  Organizations, About, etc.) do not function.

##ORCID  API technologies
All of the ORCID APIs are  based on the same set of technologies:

* **REST:** ORCID APIs are &ldquo;RESTful&rdquo;, which  means that they use HTTP (hyper-text transfer) calls to transfer information.<br />&nbsp;
* **OAuth:** ORCID  APIs use the OAuth 2.0 authentication protocol in order to grant client  applications access to users&rsquo; ORCID records.<br />&nbsp;
* **XML/JSON:** ORCID APIs support data exchange in either XML or JSON format.

##ORCID  API Tools
In order to use the ORCID  APIs you will need the following software tools:

* **Web browser:** Firefox (33+), Chrome (38+), Internet Explorer (10+), Safari (6+)
* **Internet connection**
* **Plain text editor:** TextEdit (Mac), Notepad++ (Win), or your preferred plain text editor
* **Software capable of making HTTP requests:**
    - cURL: free, command-line application available for Mac  or Windows at <a href="http://curl.haxx.se/download.html">http://curl.haxx.se/download.html</a> (pre-installed on most Mac OS versions; accessible within Terminal application)<br />&nbsp;
    - Online tools, e.g. <a href="http://hurl.it">hurl.it</a> or <a href="https://developers.google.com/oauthplayground/">Google OAuth Playground</a><br />&nbsp;
    - Your own web application, in a language such as Java,  Ruby, Python, PHP, etc.

For this workshop, we will be using <a href="https://developers.google.com/oauthplayground/">Google OAuth Playground</a>.



#OAuth BASICS
As discussed in [section 3.1](#3.1), the Public API can only be used to read and search ORCID records, and to  get authenticated ORCID iDs. The Member API, however, can be used to add new  information to ORCID records, as well as to update information previously added. To do these actions, one must obtain permission from the user/data subject. This section describes the standard OAuth process for requesting this permission.
<h2><a name="4.1"></a>4.1  Accessing the Sandbox Member API</h2>
Client credentials consisting of a client ID and a client secret are needed in order to access the Member API. Client Credentials for the Member APIs are issued by ORCID. For this workshop, you can use the sample Sandbox Client Credentials, but we recommend that you obtain your own Member API Sandbox Client Credentials using the request form at <a href="https://orcid.org/content/register-client-application" target="_blank">https://orcid.org/content/register-client-application</a> for experimintation and testing that you do outside of this workshop.

##Setting up the OAuth Playground
We&rsquo;ll use the Google Developers&rsquo; OAuth Playground for the next exercises. To get started, we will need to configure the environment to work with the ORCID Member API.

*Visit <a href="https://developers.google.com/oauthplayground" target="_blank">https://developers.google.com/oauthplayground</a><br />&nbsp; 
*Click the gear icon in the upper right corner to open the configuration form.<br />&nbsp; 
<img src="http://alainna.org/orcid/clip_image030.jpg" alt="Screen shot: Top of the screen at the Google OAuth plaground site, showing the gear icon in the upper right corner at https://developers.google.com/oauthplayground" width="530" height="60" border="0" />
*Enter the following:
<table border="1" cellspacing="0" cellpadding="0">
<tr>
  <td width="158" valign="top">**OAuth flow**</td>
  <td valign="top">Server-side</td>
  <td width="275" rowspan="7"><img src="http://alainna.org/orcid/clip_image031.jpg" alt="Screen shot: The Google OAuth plaground configuration form expanded at https://developers.google.com/oauthplayground" width="275" height="291" /></td>
</tr>
<tr>
  <td valign="top">**OAuth endpoints**</td>
  <td valign="top">Custom</td>
</tr>
<tr>
  <td valign="top">**Authorization endpoint**</td>
  <td valign="top">https://qa.orcid.org/oauth/authorize</td>
</tr>
<tr>
  <td valign="top">**Token endpoint**</td>
  <td valign="top">https://qa.orcid.org/oauth/token</td>
</tr>
<tr>
  <td valign="top">**Access token location**</td>
  <td valign="top">Authorization header    w/Bearer prefix</td>
</tr>
<tr>
  <td width="158" valign="top">**OAuth Client ID**</td>
  <td valign="top">Your Member API client ID (ex: APP-E422WM33OPZWKKMQ)</td>
</tr>
<tr>
  <td width="158" valign="top">**OAuth Client Secret**</td>
  <td valign="top">Your Member API client secret (ex: ae857cfb-446b-4c3f-8a09-55436bf602dc)</td>
</tr>
</table>
*The configuration screen should look similar to the image at right. After you&rsquo;ve entered the settings, click **Close** in the lower left corner of the configuration screen.

##Getting permission (an Access Token) to access ORCID records
To access an ORCID record via the Member API, you first need to get permission from the owner of the record in the form of an Access Token. ORCID uses the standard protocol, OAuth 2.0, to obtain this permission. Generally there are two steps:

*Get an **Authorization Code**.<br />&nbsp; 
*Exchange the Authorization Code for an **Access Token**.<br />&nbsp;


###Get an Authorization Code

<img src="http://alainna.org/orcid/clip_image033.jpg" alt="Screen shot: Google OAuth Playground, Step 1 - adding the scope variable, and clicking the 'Authorize API' button." width="288" height="177" align="right" hspace="12" vspace="12" />
To get an Authorization  Code, you&rsquo;ll need to prompt the user to sign into his/her ORCID account and  grant permission to your application. In a real-world situation, this is done  using an authorization URL that you construct. With the OAuth Playground, however, this step is done by configuring some additional settings and clicking a button.

*Beneath **Step 1: Select &amp; authorize APIs** on the left side of the Google OAuth Playground screen, type **/activities/update** in the text box (do not select any of the options presented in the box above).<br />&nbsp;
*Click the **Authorize APIs** button.<br />&nbsp; 
*<img src="http://alainna.org/orcid/clip_image035.gif" alt="Screen shot: Google OAuth Playground, Step 2 - exchanging the authorization code for tokens - the code is pre-filled after the previous step." width="315" height="136" align="right" hspace="12" vspace="12" />An ORCID OAuth permission screen will appear. If you are already signed into your test Sandbox account, click the **Authorize** button to grant permission. If you are not yet signed in, type in your test account sign in credentials, and click **Sign In** and sign into your Sandbox account and grant the permissions.<br />&nbsp; 
*Click **Authorize** on the ORCID OAuth login screen and you will be sent back to the OAuth Playground. A 6-character code will appear in the **Authorization Code **field.<br />&nbsp; 


###Exchange the Authorization Code for an Access Token
Once you have an  Authorization Code, you can exchange it for an Access Token, which allows you  to read from/write to a user&rsquo;s ORCID record. In a real-world situation, this  exchange would be done by your system, using a programming language such as  PHP, Java, or Ruby on Rails. With the OAuth Playground, however, this step is  done by clicking a button.

*<img src="http://alainna.org/orcid/clip_image036.gif" alt="" width="336" height="111" align="right" hspace="12" vspace="12" />Beneath the **Authorization Code** field, click **Exchange authorization code for tokens**. <br />&nbsp; 
*The token will appear in the **Access Token **field.<br />&nbsp; 
*Note that you are provided with additional information  in the **Request/Response **section on  the right side of the screen, such as the name and ORCID iD of the user who  granted permission, the lifespan of the token (20 years), and the scope for  which the token is valid.
<img src="http://alainna.org/orcid/clip_image038.jpg" alt="" width="340" height="103" border="0" />


#API Credential Setup
To get started setting up the institutional signin in cross-link process described in the previous section, you'll need to:

1. Get ORCID Member API credentials** (Not a member? You can use the [ORCID Public API](https://members.orcid.org/api/introduction-orcid-public-api) to get users' ORCID iDs, but you won't be able to update their ORCID records)

2. Configure identity provider settings for your API credentials

##Get ORCID Member API Credentials

To use the ORCID Member API, you'll need credentials consisting of a Client ID (consumer KEY) and Client Secret (consumer SECRET). These work like a username and password that allow your application to access the API.

We require that all new Member API applications be built and tested using our [Developer Sandbox](https://sandbox.orcid.org/signin), which mirrors production environment behavior, but does not contain production data. [Learn more about the Developer Sandbox](http://support.orcid.org/knowledgebase/articles/166623-is-the-sandbox-different-from-the-production-regis)

To get Sandbox API credentials, use the form at: 

**[Request ORCID API credentials](https://orcid.org/content/register-client-application-0)**


##Configure identity provider settings

At the moment, the process for adding identify provider settings to your API credentials is not automated. 

Instead, please send a request to [support@orcid.org](mailto:support@orcid.org) with the following information:

- Client Id
- Your identity provider entity ID (looks similar to https://idp.example.org/idp/shibboleth)
- Redirect URL the page on your site that users should be directed to after they complete the cross link process (this can be a different redirect URL than you use for other ORCID API applications)

*For new API credential requests, you can also include this info in the notes section of the request form.*

#Post an affiliation

1. Beneath **Step 3: Configure request to API**, set **HTTP Method** to **POST**.
2. Click **Add headers** and enter the following values:
      - **Header name:** accept
      - **Header value:** application/vnd.orcid+xml
<img src="http://alainna.org/orcid/clip_image040.jpg" alt="" width="464" height="119" border="0" />
3. Click **Add** to add another header and enter the following values:
    - **Header name:** Content-type
    - **Header value:** application/vnd.orcid+xml

4. Click **Add** again, then click **Close**.
5. In the **Request  URI** field, enter https://api.sandbox.orcid.org/v1.2/[orcid-id]/affiliation,  replacing [orcid-id] with the ORCID iD of the Sandbox record that you created earlier  (ex: https://api.sandbox.orcid.org/v1.2/0000-0002-3791-8427/affiliation)
<img src="http://alainna.org/orcid/clip_image042.jpg" alt="" width="392" height="232" border="0" />
6. Click **Enter request body**. Here is where you&rsquo;ll enter the XML for the works you wish to  add.
7. Visit <a href="https://git.io/vibkI" target="_blank">https://git.io/vibkI</a> and copy the XML in the **Sample Affiliation** section. 
8. Paste the copied content into the **Request Body** text box
9. Edit the text to reflect your institution. For the disambiguated-organization-identifier, replace XXXXXX with the Ringgold identifier for your institution listed **Ringgold List**
10. Click **Close**.
<img src="http://alainna.org/orcid/clip_image044.jpg" alt="" width="498" height="275" border="0" />
11. Click **Send the  request**.
12. The  results will appear in the **Request/Response** section on the right side of the screen. Scroll to the bottom – if you see **HTTP/1.1 201 Created**, the work was  successfully posted!
<img src="http://alainna.org/orcid/clip_image046.jpg" alt="" width="483" height="224" border="0" />
13. Visit the **public  view **of your Sandbox record at http://sandbox.orcid.org/[Your sandbox iD]  to see the work that you added in the user interface.

##Update an affiliation

In a real-world situation, you may need to update a researcher's affiliation.

1. Click **Enter request body**. This is where you&rsquo;ll  enter the XML for the work that you wish to edit.
2. Visit <a href="http://git.io/vITI9" target="_blank">http://git.io/vITI9</a> and copy the XML in the **Sample Affiliation Updated** section. *(Tip: The amended area are lines 14-18, beginning with &lt;end-date&gt;. You can paste it after the &lt;/start-date&gt; in the active Request Body.)*
3. Paste the copied content into the **Request Body** field and amend to reflect your institution.
4. Click **Close**.
5. Click **Send the Request**.
6. The  results will appear in the **Request/Response** section on the right side of the screen. If the full XML of the user&rsquo;s  record appears, the work was successfully updated! If you receive an error, be sure to check that the headers value under **Add headers** have not been changed to garbled text, e.g. "application%2Fvnd.orcid%2Bxml". 
7. Visit  the public view of your Sandbox record at http://sandbox.orcid.org/[Your  sandbox iD] to see the changes to the work in the user interface.

#Reference

* See example implementations and workflow guides <a href="https://members.orcid.org" target="_blank">https://members.orcid.org</a><br />&nbsp;
* Read technical documentation <a href="https://members.orcid.org/api" target="_blank">https://members.orcid.org/api</a><br />&nbsp;
* Join the ORCID API Users Group <a href="https://groups.google.com/group/orcid-api-users" target="_parent">https://groups.google.com/group/orcid-api-users</a><br />&nbsp;
* Sign up for a Technical Webinar <a href="https://members.orcid.org/event-list">https://members.orcid.org/event-list</a><br />&nbsp;
* Email ORCID Support <a href="mailto:support@orcid.org">support@orcid.org</a>

