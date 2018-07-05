
##Other methods for getting authorised iDs

You have just followed a method a custom integration would use to get ORCIDs from users. The following

##Vendor systems

Some publishing, research information and repository software systems support collecting authenticated iDs and permissions right out of the box. See our list of [ORCID-enabled systems](https://members.orcid.org/api/orcid-enabled-systems) for more details.

Configuration steps and customization options vary widely between systems - check your system's documentation for complete information.

##Institutional sign-in

ORCID recently added the option to sign in using institutional credentials. Institutional sign-in is available to researchers affiliated with members of supported identity federations, currently [SURFconext](https://www.surf.nl/en/services-and-products/surfconext/index.html) and [eduGAIN](https://technical.edugain.org/status.php).

ORCID membership is not required in order for institutional sign-in to work for your researchers, however, ORCID members who are [SURFconext](https://www.surf.nl/en/services-and-products/surfconext/index.html) or [eduGAIN](https://technical.edugain.org/status.php) federation members can automatically request ORCID iDs and ORCID record access permission from users who sign into ORCID with their institutional credentials using the new Institutional Collect & Connect feature.

In this section, we'll take a look at this feature. [Learn more about ORCID institutional signin, including configuring up your IdP](https://members.orcid.org/api/integrate/institution-sign-in)

###Configure API credentials
In addition to getting Member API credentials as described above, ORCID will need a few more pieces of information to set up Institutional Collect & Connect for your organization.

To have your API credentials configured for Institutional Collect & Connect, contact [support@orcid.org](support@orcid.org) with the following information:

* Client ID
* Identity provider entity ID (e.g. https://idp.example.org/idp/shibboleth)
* Redirect URI: The page on your site that users should be directed to after they complete the cross-link process. This can bedifferent from the redirect URI you use for other ORCID API applications.
* Permission scope(s) that you would like (```/authenticate```, ```/read-limited```, ```/activities/update```, ```/person/update```)

###(User) Connect your institutional account

**Not a member of a supported federation?** Test out ORCID institutional sign-in with a [United ID](https://app.unitedid.org/signup) account. United ID is a free and independent online identity service *(Note: United ID requires use of a 2-Factor Authentication method, like [Google Authenticator](https://support.google.com/accounts/answer/1066447?hl=en))*.

  1. Sign out of your Sandbox record - click the **Sign out** button in the upper right corner or visit [https://sandbox.orcid.org/signout](https://sandbox.orcid.org/signout)
  2. Visit [https://sandbox.orcid.org/signin](https://sandbox.orcid.org/signin) and click **Sign in using your Institutional Account**
  3. Enter your organization's name in the box, or choose to pick it from the list.
  <img src="../images/04-3_signin-inst-account.png" width="400" alt="ORCID sign-in screen showing institutional account sign-in">
  4. Sign into your institution account<br>
  <img src="../images/04-3_united-id-login.png" width="400" alt="United ID login screen">
  5. Finish linking your accounts by signing into ORCID with your ORCID username and password. Enter the email address / ORCID iD and password for your Sandbox account and click **Sign into ORCID**. *You will only need to complete this step once - in the future you can log directly into ORCID with your institutional account.*<br>
  <img src="../images/04-3_link-account.png" width="600" alt="ORCID link accounts screen">
  6. After linking your accounts, a message appears at the top of your ORCID record, prompting you to connect your iD to your institution. Click the **Connect** button.<br>
  <img src="../images/04-3_inst-connect-banner.png" width="600" alt="ORCID record showing institution connect message" />
  7. An ORCID sign-in screen listing the requested permissions will appear; click **Authorize**<br>
  <img src="../images/04-3_inst-connect-oauth.png" width="400" alt="ORCID OAuth sign-in screen" />
  8. After granting permission, you'll be redirected to the Redirect URI specified for your API credentials - this page should show a success or error message depending on whether **Authorize** or **Deny** was clicked, and it should also provide a link back to ORCID and links to your local ORCID resources.<br>
  <img src="../images/04-3_inst-connect-redirect.png" width="600" alt="Example success message shown to users after completing the institution connect process" />

###Exchange authorization code for access token & authenticated iD
Like in section 4.1.4 above, an authorization code is attached to the end of the redirect URI, which can be exchanged for an access token and the user's ORCID iD.<br>
  <img src="../images/04-3_inst-connect-auth-code.png" width="600" alt="Browser address bar showing OAuth authorization code" />

##Share my iD

Need a quick way to collect authenticated iDs with no programming or IT resources needed?
[Share my iD](https://share-my-id.orcid.org/) is a new app from ORCID that allows anyone with an ORCID iD to get iDs from other ORCID users.<br>
  <img src="../images/04-4_share-my-id.png" width="600" alt="ORCID Share my iD app home page" />

##DOI metadata

Many systems now collect authenticated ORCID iDs and publish them in DOI (and other persistent identifier) metadata. If you have a DOI for a publication, dataset, or other digital object, you can check its metadata for author ORCID iDs.

###Example: CrossRef API
For example, using the [CrossRef REST API](https://github.com/CrossRef/rest-api-doc/blob/master/rest_api.md), we can find an author's ORCID iD in the DOI metadata for ```http://dx.doi.org/10.1155/2013/364301```

1. In a new window or tab, visit ```https://api.crossref.org/v1/works/10.1155/2013/364301```
2. In the JSON data that appears, ORCID iDs submitted by the publisher in the DOI metadata are included in the ```author``` element.
<br>
  <img src="../images/04-5_doi-metadata.png" width="400" alt="ORCID in DOI metadata" />
