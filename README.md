For mock-up OAuth, download https://mockoon.com/download/

To setup mockoon:

Step 1: Create a New Environment

- Open Mockoon and click the "+" (New Environment) button in the top left.
	
- Give it a name (e.g., Mule-Mock-IdP).
	
- Set the Port (e.g., 3001) so it doesn't conflict with your Mule app (usually 8081).
	

Step 2: Create the /token Route

- Click "Add Route" (the + icon next to the filter bar).

- Set the method to POST.

- Set the path to /token.
	
Step 3: Define the JSON Response

- In the Body tab of the route, paste a standard OAuth 2.0 response body:

	{
	"access_token": "mock-token-12345",
	"token_type": "Bearer",
 	"expires_in": 3600,
  	"scope": "read write"
	}


Step 5: Run and Test

- Click the Green Play Button at the top to start the server.
- Test it using cURL or Postman:

	curl -X POST http://localhost:3001/token

Step 6: Update Mule 4 Configuration

- In your Mule 4 project, update your HTTP Request or OAuth 2.0 Client Credentials 	configuration:
  
	Token URL: http://localhost:3001/token

	Client ID/Secret: (You can put anything, since the mock doesn't validate them unless you add "Rules" in Mockoon).
