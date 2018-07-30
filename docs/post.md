Now that we've got an Access Token, we can use it like a password to take the API actions we requested permission for.

 In this section, we'll add an education affiliation to our Sandbox record. You can use the API to, POST (add), PUT (update), DELETE, or read any section of the record, the only things you need to change are the endpoints and the XML for each section. In the following example we are using the /education endpoint with the [correct XML](https://github.com/ORCID/ORCID-Source/blob/master/orcid-model/src/main/resources/record_2.1/samples/write_sample/education-2.1.xml) to add the information, but you can just as well add Employment or Works for example. See our [Github documentation](https://github.com/ORCID/ORCID-Source/blob/master/orcid-model/src/main/resources/record_2.1/README.md) for more example files and endpoints and the permissions you need for each.

##Add an education affiliation
Still have that Google OAuth Playground window open? If so, continue with step 1 below. If not, go back and repeat the [Get an authorization code](/collect/#get-an-authorization-code) and [Exchange authorization code for an access token](/collect/#exchange-authorization-code-for-access-token-authenticated-id) steps from the previous section before moving on to the steps below.

1. Beneath **Step 3: Configure request to API**, set **HTTP Method** to **POST**.<br>
<img src="../images/06-1_http-method-post.png" width="400" alt="Google OAuth Playground HTTP method set to POST" />
2. Click **Add headers**, enter the values below, then click **Add** and **Close**
    - **Header name:** ```accept```
    - **Header value:** ```application/vnd.orcid+xml```
<br>
<img src="../images/06-1_header-accept.png" width="400" alt="Google OAuth Playground adding accept header" />
5. In the **Request URI** field enter:<br>
```https://api.sandbox.orcid.org/v2.0/[ORCID ID]/education```<br>
*Replace [ORCID ID] with the iD for your Sandbox record, format XXXX-XXXX-XXXX-XXXX*<br>
<img src="../images/06-1_request-uri.png" width="400" alt="Google OAuth Playground request URI configuration for adding an education affiliation" />
3. Click **Content-type** > **Custom** and enter ```application/vnd.orcid+xml```<br>
<img src="../images/06-1_headers.png" width="400" alt="Google OAuth Playground Content-type header configuration" />
4. Click **Add**, then click **Close**.
6. Click **Enter request body**.
7. Copy the education affiliation XML at the end of this section and paste it into the **Request Body** text box<br>
<img src="../images/06-1_request-body.png" width="600" alt="Google OAuth Playground Request Body configuration for new education affiliation" />
9. **OPTIONAL:** In the **Request Body** text box, edit the XML to reflect your institution.<br>
*For ```<disambiguated-organization-identifier>```, use the [Ringgold Identify database](https://www.ringgold.com/identify/) to find the Ringgold ID for your institution (you'll need to [register a free Ringgold account](https://ido.ringgold.com/register) in order to search the database).*
10. Click **Close**.
11. Click **Send the  request**.
12. The  results will appear in the **Request/Response** section at right. Scroll to the bottom – if you see **HTTP/1.1 201 Created**, your education affiliation was successfully added!<br>
<img src="../images/06-1_post-affiliation-response.png" width="600" alt="Google OAuth Playground response for successful education affiliation POST request" />
13. Visit the public view of your Sandbox record at ```https://sandbox.orcid.org/[ORCID ID]``` to see your new education affiliation.<br>
<img src="../images/06-1_new-affiliation.png" width="600" alt="ORCID record with new education affiliation item added" /><br>
*Notice that **Source** shows the name of the API client that added the affiliation - this is a key element that helps other systems consuming ORCID data determine whether this piece of information is authoritative.**

##Education affiliation XML

```
<?xml version="1.0" encoding="UTF-8"?>
<education:education
  xmlns:common="http://www.orcid.org/ns/common" xmlns:education="http://www.orcid.org/ns/education"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://www.orcid.org/ns/education ../education-2.0.xsd ">
  <education:department-name>Department</education:department-name>
  <education:role-title>Degree title</education:role-title>
  <common:start-date>
    <common:year>2012</common:year>
    <common:month>01</common:month>
    <common:day>01</common:day>
  </common:start-date>
  <education:organization>
    <common:name>ORCID</common:name>
    <common:address>
      <common:city>Bethesda</common:city>
      <common:region>Region</common:region>
      <common:country>US</common:country>
    </common:address>
    <common:disambiguated-organization>
      <common:disambiguated-organization-identifier>385488</common:disambiguated-organization-identifier>
      <common:disambiguation-source>RINGGOLD</common:disambiguation-source>
    </common:disambiguated-organization>
  </education:organization>     
</education:education>
```
