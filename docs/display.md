#7. DISPLAY: PRESENTING ORCID IN YOUR SYSTEM

##Display ORCID iDs

Researchers want to know that using their iD in your system has had some effect. The best way to signal that the collected iD is actually put to use is to display it - in your web applications, in publications, with funding awards, etc.

For authenticated iD's show the iD icon followed by the full iD URI, linked to the iD URI:

<a href="https://orcid.org/0000-0002-1825-0097"> <img alt="ORCID iD" class="icon" src="../images/orcid_16x16.gif" style="width:16px; height:16px; margin-right:4px; margin-left:4px">https://orcid.org/0000-0002-1825-0097</a>

For more details, see our [Trademark and iD Display Guidelines](https://info.orcid.org/brand-guidelines/)

<img src="../images/07_1_kaken_profile_system.png" width="600" alt="ORCID iD displayed on Kaken Profile System for SUENAGA Kiyotake" />

You can also just show the iD icon next to the researcher's name as seen in the screenshot below.

<img src="../images/07_1_Orcid_id_journal_functional_ecology.png" width="600" alt="ORCID iD displayed in Journal of Functional Ecology article" />

##Presenting the ORCID OAuth screen & redirect pages

In order to provide a consistent experience for users, we recommend following the guidelines below for presenting ORCID OAuth in your system. For more details, see our help doc on [Presenting OAuth](https://info.orcid.org/documentation/integration-guide/customizing-the-sign-in-register-screen/).

###1. Use a button or link to connect users to ORCID via OAuth

See [example buttons and links](https://info.orcid.org/documentation/integration-guide/customizing-the-sign-in-register-screen/#use-button)

<img src="../images/07-2_link-id-button.png" width="400" alt="Example manuscript submission form with 'Create or Connect your iD' button" />

###2. Include text describing ORCID and a link to the ORCID website

See [sample text](https://info.orcid.org/documentation/integration-guide/customizing-the-sign-in-register-screen/#include-text)

<img src="../images/07-2_orcid-text.png" width="400" alt="Example manuscript submission form with info about ORCID" />

###3. Present the OAuth sign-in screen as a popup or modal window

The OAuth screen is designed to look best at a maximum width of 500px.

<img src="../images/sandbox-oauth.png" width="400" alt="ORCID OAuth screen" />

###4. Provide an appropriate redirect page and close the OAuth window

Remember that users can either authorize or deny access - make sure to show a different message for each case.

<img src="../images/07-2_redirect.png" width="300" alt="Example OAuth redirect screen" />
