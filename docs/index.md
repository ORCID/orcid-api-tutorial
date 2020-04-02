##About ORCID

ORCID provides an identifier for researchers _AND_ tools (like APIs) to help make connections between researchers, their contributions, and affiliations. **Why?** To help people find information, and to simplify reporting and analysis.

ORCID wants to help make it possible to do things like:

* Find all of a researcher’s work with a single query
* Auto-populate manuscript submission and grant application forms
* Get (nearly) real-time data about researchers’ publications and grants
* Find the current affiliation(s) of any researcher

ORCID can't do this on its own - integrations with other systems (like manuscript submission/production, funding application, repository, research information, and directory systems) are essential.

##About this tutorial

This tutorial provides an introduction to integrating ORCID into your systems, so that, together, we can help everyone involved in research spend more time *making* contributions and less time *managing* them!

In this tutorial you will learn:

 * The types of ORCID APIs and what you can do with them
 * How to get set up with the ORCID sandbox to test your API integration
 * How to read and search information from the public API
 * What a Client ID and Client Secret is and how to use them
 * How to get an access token using the mysterious 3-legged OAuth process


##Pre-requisites
 To complete this tutorial, you'll need the following tools:

 * **Web browser:** ([that's up to date](https://support.orcid.org/knowledgebase/articles/1804765-technical-requirements-for-using-the-orcid-site))
 * **Internet connection**
 * **Plain text editor:** TextEdit (Mac), Notepad++ (Win), or your preferred plain text editor
 * **Software capable of making HTTP requests:**

 Examples in this doc use [Google OAuth Playground](https://developers.google.com/oauthplayground/)

 You can also use
 		- [cURL](http://curl.haxx.se/download.html): Free, command-line application available for Mac  or Windows (pre-installed on most Mac OS versions;   accessible within Terminal application)
     - Or other online tools, like [Insomnia](https://insomnia.rest/)

 Once you have got to grips with the APIs you can use our [Swagger](https://pub.sandbox.orcid.org/v2.0/) graphical interface.


##About the ORCID APIs
ORCID's web interface gives researchers a way to interact with their record, but the real power of ORCID lies in the underlying data, which can be accessed by people and systems via Application Programming Interfaces (APIs).

* **Public API:** Free to anyone with an ORCID iD
* **Member API:** Available to ORCID [member organizations](https://orcid.org/about/membership) (Sandbox Member API freely available for testing)
* **Premium Member API** Available to ORCID premium member organizations (Sandbox Member API freely available for testing)

| Features       | Public API | Member API |Premium Member API |
| -------------- | ---------- | ---------- | ----------------- |
Authenticate: Get a user’s authenticated ORCID iD|yes|yes|yes|
Read (Public): Read public data on ORCID records|yes|yes|yes|
Create: Help researchers register for an ORCID iD using our create-on-demand process |yes|yes|yes|
Read (Limited): Read limited-access data on ORCID records|no|yes|yes|
Add: Post new items to a record|no|yes|yes|
Update: Edit or delete items you previously added|no|yes|yes|
Integration with your system using an API client |no|yes one only|yes up to five|
Webhooks: Receive notifications of updates to your users' ORCID records|no|no|yes|

All of the ORCID APIs are  based on the same set of technologies:

* **REST:** ORCID APIs are &ldquo;RESTful&rdquo;, which  means that they use HTTP to transfer information.
* **OAuth:** ORCID  APIs use the [OAuth 2.0 authentication protocol](https://oauth.net/2/) to grant client  applications access to users&rsquo; ORCID records.
* **XML/JSON:** ORCID APIs support data exchange in either XML or JSON format.

[Learn more about the ORCID APIs](https://members.orcid.org/api/about-orcid-apis)
