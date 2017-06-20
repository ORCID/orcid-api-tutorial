In a real-world situation, you may need to update a researcher's affiliation. In this section, we'll update our education affiliation to include an end date.

##Update an education affiliation

1. In the **Request/Response** section at right, find the **put-code** for the education affiliation that you added in the previous section.<br>
<img src="../images/06-2_put-code.png" width="600" alt="Detailed view of Google OAuth Playground response for successful education affiliation POST request showing put-code" />
2. Change **HTTP Method** to **PUT**<br>
<img src="../images/06-2_http-method-put.png" width="400" alt="Google OAuth Playground HTTP method set to PUT" />
3. Click **Add Headers** and make sure that ```accept``` and ```Content-type``` are both set to ```application/vnd.orcid+xml```<br>
<img src="../images/06-2_put-headers.png" width="400" alt="Google OAuth Playground accept and Content-type header configuration" />
3. In the **Request URI** field enter:<br>
```https://api.sandbox.orcid.org/v2.0/[ORCID ID]/education/[PUT CODE]```<br>
*Replace [ORCID ID] with the iD for your Sandbox record, format XXXX-XXXX-XXXX-XXXX and [PUT CODE] with the put-code for your education affiliation*<br>
<img src="../images/06-2_request-uri.png" width="400" alt="Google OAuth Playground request URI configuration for updating an education affiliation" />
2. Click **Enter request body** (the XML for the affiliation you added in the previous step should appear).
3. Inside the ```<education:education``` tag, add ```put-code=[PUT CODE]```<br>
*Replace [PUT CODE] with the put-code for your education affiliation, ex ```<education:education put-code="26971"```*<br>
<img src="../images/06-2_request-body-1.png" width="600" alt="Google OAuth Playground Request Body configuration for updating an education affiliation showing where to place put-code" />
4. Copy the affiliation end date XML at the end of this section and paste it beneath the ```</common:start-date>``` tag (and above the ```<education:organization>``` tag)<br>
<img src="../images/06-2_request-body-2.png" width="600" alt="Google OAuth Playground Request Body configuration for updating an education affiliation showing where to place end-date XML" />
5. Click **Close**.
6. Click **Send the Request**.
7. The  results will appear in the **Request/Response** section at right. Scroll to the bottom – if you see **HTTP/1.1 200 OK**, your education affiliation was successfully updated! If you see an error message, check that the header values in **Add headers** have not been changed to garbled text, ex: ```application%2Fvnd.orcid%2Bxml"```<br>
<img src="../images/06-2_put-affiliation-response.png" width="600" alt="Google OAuth Playground response for successful education affiliation PUT request" />
8. Visit the **public  view** of your Sandbox record at ```http://sandbox.orcid.org/[ORCID ID]``` to see your updated education affiliation.<br>
<img src="../images/06-2_updated-affiliation.png" width="600" alt="ORCID record with updated education affiliation item" /><br>

##Affiliation end date XML

```
<common:end-date>
  <common:year>2017</common:year>
  <common:month>01</common:month>
  <common:day>31</common:day>
</common:end-date>
```
