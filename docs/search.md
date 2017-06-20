In addition to reading information on a specific ORCID record, you can use the API to search for ORCID records that contain specific information.

In this section, we'll try searches using just a few of the available fields. For a full list of fields that you can search, see our [Basic tutorial: Searching Data using the ORCID API](https://members.orcid.org/api/tutorial/search-orcid-registry)

##Search for records with an institutional affiliation
1. In a new window or tab, visit [https://developers.google.com/oauthplayground](https://developers.google.com/oauthplayground)
2. On the left side of the screen, click **Step 3 Configure request to API**
3. In the **Request URI** field enter:<br>
```https://pub.sandbox.orcid.org/v2.0/search/?q=affiliation-org-name:%22Boston%20University%22```<br>
*Optional: <br>
<img src="../images/02-1_request-record.png" width="400" alt="Google OAuth Playground request for ORCID record summary" />
4. Click **Send the request**
5. The total number of matching ORCID iDs and a list of those iDs will appear **Request/Response** section<br>
<img src="../images/02-1_response-record.png" width="600" alt="Google OAuth Playground response for ORCID record summary" />

##Paging search results
If your search matches more than 100 ORCID iDs, only the first 100 iDs will be returned in the list of results. To get the next set of results, you'll need to make another API request.

1. On the left side of the screen, click **Step 3 Configure request to API**
2. In the **Request URI** field enter:<br>
```https://pub.sandbox.orcid.org/v2.0/search/?q=affiliation-org-name:%22Boston%20University%22&start=101&rows=200```<br>
3. Click **Send the request**
4. The total number of matching ORCID iDs and a list of iDs 101-301 will appear in the **Request/Response** section<br>
<img src="../images/02-1_response-record.png" width="600" alt="Google OAuth Playground response for ORCID record summary" />

To get the entire set of results, repeat the query in step 2, changing ```start=``` until you've reached collected all of your results.