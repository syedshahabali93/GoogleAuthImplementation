# GoogleAuthImplementation OAuth2.0
How to implement Google OAuth2 in your script if you only have back-end (no front-end) and cannot support redirections


Create a new Project in Cloud Console:
1. Navigate to https://console.cloud.google.com/ and create a new project
2. Enter project name
3. Click Create
4. Select the newly created project from the notifications pop-up on the right
5. Click on search bar at the center
6. Enter spreadsheets
7. Select Google Sheets API from the search results under the Marketplace
8. After getting re-directed to Google Sheets API page click Enable button
9. After page load click on Create Credentials on top right
10. After page load click on Credential Type 'Which API are you using?' input field and select Google Sheets API
11. Click on User data radio button
12. Click Next
13. Enter App name 'SpreadSheetApp'
14. Enter your gmail id in User Support Email field
15. Enter your gmail id in Developer Contact Information field
16. Click Save and Continue button
17. Click on Add or Remove Scopes button
18. Enter spreadsheet in the search bar in the Update selected scopes popup on right
19. Find 'https://www.googleapis.com/auth/spreadsheets' in the results and click on the checkbox to select it
20. Click on Update button
21. Click on Save and Continue button
22. Select Application type 'Web Application'
23. Click Add URI button under 'Authorized redirect URI's
24. Enter http://localhost in the URI's input field
25. Click Create
26. Copy Client-ID and download the credentials file
27. Click on 'OAuth consent screen page' below Download button
28. Click on Add Users button under Test Users
29. Enter your own email id in the Add Users popup on the right
30. Click Save
31. Click on Done button
32. Open credentials file downloaded in Notepad++ and extract client_secret value
33. Download the collection share in the github project
34. Import the collection in Postman
35. A collection with name 'Spreadsheet Authentication' will be shown
36. Select the first API GEt request from the collection
37. Click on Params
38. Replace scope with https://www.googleapis.com/auth/spreadsheets
39. Set access_type value offline
40. Set redirect_uri value http://localhost
41. Set response_type value code
42. Set client_id value copied from cloud console
43. Now copy the generate url from the top input field and paste in the browser
44. Hit enter
45. Copy the redirect url in Notepad++
46. Extract code
47. Click on the second Post request in the collection
48. Replace code value with the newly extracted code
49. Replace client_id with downloaded client_id
50. Replace client_sected with extracted client_secret from credentials.json file
51. Replace redirect_uri with http://localhost
52. Click Send button on the api call
53. You'll receive access_token, refresh_token and some other values in response
54. Access Token is the value used to perform API calls
55. In case access_token is expired then refresh_token can be used to generate new access_token
56. For generating new access_token copy the refresh_token from the response of 2nd API Post request in the collection
57. Select the 3rd API Post request in the collection and replace with refresh_token value
58. Replace client_id and client_secret with the downloaded and extracted values
59. Click on Send button
