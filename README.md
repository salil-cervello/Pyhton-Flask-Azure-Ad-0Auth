# Pyhton-Flask-Azure-Ad-0Auth
Python Flask Azure ad oauth 
Azure App Registration.
1. Register your Azure AD v2.0 app.  
    - Navigate to the [Azure Portal Active Directory Blade](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade)
    - Go to the `Application Registrations` blade
    - From the Toolbar click on `+ New application registration`
    - Enter a Name for the application - `Any Name(Without Space) ` works fine
    - Make sure that you Select `Web app/API` is selected for the **Application Type**
    - Enter the Return URL for this sample - `http://localhost:5000/getAToken`.  -  make sure it's exactly that value.
    - Click the `Create` button
    - Once Created, click on the app in the Application Registration List - **NOTE:** You may have to click on `View All Applications` button to see. If you are unble to view your recently created application.
    - In the Application Blade - From Left navigation select Certificates & secrets. (For your secret key).
	- In Client Secret Section, click on New Client Secret Key button to Generate new secret key.
	- Add a client secret Window Add `Key Description` Test and Set expiry Duration date - 1 year is fine for this sample,	
    - Click on `Save` on the Toolbar
    - Once Saved, ensure you capture the secret key Value - it will be a 44 characters long string
    
app_config.py
```
CLIENT_SECRET = <from App Registration secret key>
AUTHORITY = "https://login.microsoftonline.com/68932627-def8-4e45-ac72-14df51d766c2"
CLIENT_ID = <from App Registration Cleint id>
REDIRECT_PATH = "/getAToken"
ENDPOINT = 'https://graph.microsoft.com/v1.0/users'
```
1. You can give api access perrmission for indual apps - Azure Data Explorer , Office 365 Management APIs 

1. From `Organizational relationships | Users from other organizations` , we add new member and block the member within the organisation oe outside the organisation to access the app ,using thier email id's , and assigning thier roles. 


