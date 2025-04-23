#  Create OAuth 2.0 Credentials in Google Cloud for Microsoft Sentinel
 
This guide helps create the required **Client ID** and **Client Secret** in **Google Cloud Platform (GCP)** so logs can be securely sent to **Microsoft Sentinel**.
 
---
 
##  What You’ll Need
 
- A **Google account**
- Access to your organization's **Google Cloud Project**
- Access to **Google Cloud Console** at [https://console.cloud.google.com/](https://console.cloud.google.com/)
 
---
 
##  Why Are We Doing This?
 
To allow Microsoft Sentinel (a security system) to access logs from your Google Cloud account, we need to give it **secure permission** using a method called **OAuth 2.0**.
 
This requires:
- A **Client ID**
- A **Client Secret**
 
---
 
## 🪜 Step-by-Step Instructions
 
### Step 1: Log In to Google Cloud Console
 
- Go to: [https://console.cloud.google.com/](https://console.cloud.google.com/)
- Sign in using your Google account.
- Choose the correct project (top menu bar).
 
---
 
### Step 2: Enable Required Services (APIs)
 
1. Go to: [https://console.cloud.google.com/apis/library](https://console.cloud.google.com/apis/library)
2. Use the search box and **enable these three services** one by one:
   - **Cloud Monitoring API**
   - **Cloud Logging API**
   - **IAM API**
3. For each one, click on it, then click the blue **"Enable"** button.
 
---
 
### Step 3: Set Up the Consent Screen (Only once)
 
1. Go to: [https://console.cloud.google.com/apis/credentials/consent](https://console.cloud.google.com/apis/credentials/consent)
2. Select **"External"**, then click **"Create"**
3. Fill in:
   - **App Name**: Sentinel Connector
   - **User Support Email**: your email
   - **Developer Contact Info**: your email again
4. Click **"Save and Continue"** until it’s done (you don’t need to fill everything)
 
---
 
### Step 4: Create OAuth 2.0 Credentials
 
1. Go to: [https://console.cloud.google.com/apis/credentials](https://console.cloud.google.com/apis/credentials)
2. Click **"Create Credentials"** → choose **"OAuth client ID"**
3. Choose **"Web application"** as the type
4. Give it a name: `Sentinel OAuth`
5. Scroll to **Authorized redirect URIs** and paste this link:"https://portal.azure.com/TokenAuthorize/ExtensionName/Microsoft_Azure_Security_Insights"
6. Click **"Create"**
 
---
 
### Step 5: Save the Credentials
 
After creation, you’ll see:
- A **Client ID**
- A **Client Secret**
 
 Copy both values and **save them securely**. You’ll need them for Microsoft Sentinel.
 
You can also click **"Download JSON"** to save them in a file.
 
---
 
## Step 6: Use These in Microsoft Sentinel
 
When connecting Google Cloud logs in Microsoft Sentinel:
- Paste the **Client ID** and **Client Secret** you just created.
- This will allow Sentinel to access the logs securely.
 
---
