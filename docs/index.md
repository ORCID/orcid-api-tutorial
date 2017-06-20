#WELCOME!
##About the ORCID APIs
ORCID's web interface gives researchers a way to interact with their record, but the real power of ORCID lies in the underlying data, which can be accessed by people and systems via Application Programming Interfaces (APIs).

| API&nbsp;Version   | Access | Features |
| -------------- | ------ | --- |
**Public&nbsp;API** | Freely available to anyone | **Authenticate:** Obtain a user&rsquo;s authenticated ORCID iD<br> **Read (Public):** Search/retrieve public data<br> **Create:** Create new ORCID records on demand
**Member&nbsp;API** | Available to organizations that support ORCID with an annual membership subscription<br>*(Sandbox Member API freely available to all for testing)* | All Public API features, plus:<br> **Read (Limited):** Search/retrieve public data<br> **Update:** Post new items to a record (affiliations, works, etc.) or edit items that you added previously

All of the ORCID APIs are  based on the same set of technologies:

* **REST:** ORCID APIs are &ldquo;RESTful&rdquo;, which  means that they use HTTP (hyper-text transfer) calls to transfer information.
* **OAuth:** ORCID  APIs use the OAuth 2.0 authentication protocol in order to grant client  applications access to users&rsquo; ORCID records.
* **XML/JSON:** ORCID APIs support data exchange in either XML or JSON format.

##Pre-requisites
To complete this tutorial, you'll need the following tools:

* **Web browser:** Firefox (33+), Chrome (38+), Internet Explorer (10+), Safari (6+)
* **Internet connection**
* **Plain text editor:** TextEdit (Mac), Notepad++ (Win), or your preferred plain text editor
* **Software capable of making HTTP requests:**
    - cURL: Free, command-line application available for Mac  or Windows at <a href="http://curl.haxx.se/download.html">http://curl.haxx.se/download.html</a> (pre-installed on most Mac OS versions; accessible within Terminal application)
    - Online tools, like [Google OAuth Playground](https://developers.google.com/oauthplayground/) or [hurl.it](http://hurl.it">hurl.it)

Examples in this doc use [Google OAuth Playground](https://developers.google.com/oauthplayground/)