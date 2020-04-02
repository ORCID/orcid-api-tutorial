
 In this section, we'll add an education affiliation to our Sandbox record. As you have seen you can use the API to GET (read) items on the record, you can also POST (add), PUT (update), DELETE, any section of the record, the only things you need to change are the endpoints and the XML for each section. In the following example we are using the /education endpoint with the [correct XML](https://github.com/ORCID/ORCID-Source/blob/master/orcid-model/src/main/resources/record_3.0/samples/write_sample/education-3.0.xml) to add the information, but you can just as well add Employment or Works for example. See our [Github documentation](https://github.com/ORCID/ORCID-Source/blob/master/orcid-model/src/main/resources/record_3.0/README.md) for more example files and endpoints and the permissions you need for each.

##Add an education affiliation
 Still have that Google OAuth Playground window open? If so, continue with step 1 below. If not, you have two options, If you saved your authorization token from earlier fill out the Oauth Playground window as you had it on [Read the record](read.md)  or if not, go back and repeat the [Get an authorization code](get.md) and [Exchange authorization code for an access token](get.md#Exchange-authorization-code-for-access-token-and-authenticated-iD) steps from the previous section before moving on to the steps below. -->

1. Beneath **Step 3: Configure request to API**, set **HTTP Method** to **POST**.<br>
<img src="../images/06-1_http-method-post.png" width="400" alt="Google OAuth Playground HTTP method set to POST" />
2. Click **Add headers**, remove any previous headers and enter the values below, then click **Add** and **Close**
    - **Header name:** ```accept```
    - **Header value:** ```application/vnd.orcid+xml```
<br>
<img src="../images/06-1_header-accept.png" width="400" alt="Google OAuth Playground adding accept header" />
5. In the **Request URI** field enter:<br>
```https://api.sandbox.orcid.org/v3.0/[ORCID ID]/education```<br>
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
	xsi:schemaLocation="http://www.orcid.org/ns/education ../education-3.0.xsd ">	
	<common:department-name>department-name</common:department-name>
	<common:role-title>role-title</common:role-title>
	<common:organization>
		<common:name>common:name</common:name>
		<common:address>
			<common:city>common:city</common:city>
			<common:region>common:region</common:region>
			<common:country>AF</common:country>
		</common:address>
		<common:disambiguated-organization>
            <common:disambiguated-organization-identifier>http://dx.doi.org/10.13039/100000001</common:disambiguated-organization-identifier>
			<common:disambiguation-source>FUNDREF</common:disambiguation-source>
        </common:disambiguated-organization>
	</common:organization>		
	<common:url>http://tempuri.org</common:url>  
	<common:external-ids>
        <common:external-id>
            <common:external-id-type>grant_number</common:external-id-type>
            <common:external-id-value>external-identifier-value</common:external-id-value>          
            <common:external-id-url>http://tempuri.org</common:external-id-url>
            <common:external-id-relationship>self</common:external-id-relationship>
        </common:external-id>
        <common:external-id>
            <common:external-id-type>grant_number</common:external-id-type>
            <common:external-id-value>external-identifier-value2</common:external-id-value>         
            <common:external-id-url>http://tempuri.org/2</common:external-id-url>
            <common:external-id-relationship>self</common:external-id-relationship>
        </common:external-id>
    </common:external-ids>
</education:education>
```
