Here's the guide converted to markdown:

```markdown
# How to Connect Google APIs to n8n

This guide will help you configure your Google Cloud Console (GCP) and integrate services such as Google Drive, Gmail, Google Docs, Sheets, Slides, and Calendar with n8n.

## Step 1: Visit GCP
Visit the Google Cloud Console (GCP) at:  
[https://console.cloud.google.com/](https://console.cloud.google.com/)  
Select the right Gmail account.

## Step 2: Payment Settings and Verification
You will need to input your card details.  
You must use a physical Mastercard or Visa card, without any local restrictions.  
Otherwise, Google will not accept the card, and you won't be able to proceed with the setup.

> **Note:**  
> - You will not be charged.  
> - If it's your first time, you'll receive $300 Google Cloud credits (valid for 3 months).

## Step 3: Create a Project
You will have a default project called “My First Project” or “No Organization”.  
You can create a new project and give it a preferred name.  
For example: **n8n connection**

In the top-left corner, click on “My First Project”.  
Switch to the new project you just created.

## Step 4: Enable APIs
We’re going to enable all APIs, following a 3-step process:  
1. In GCP, at the top, search for **Google Drive API**.  
2. Click the Google Drive API result.  
3. Then click **Enable**.

Repeat steps 1-3 for the following APIs:  
- Gmail API  
- Google Docs API  
- Google Sheets API  
- Google Calendar API  
- Google Slides API

## Step 5: OAuth Consent Screen
1. Hit the hamburger helper in the top left corner.  
2. Click **“APIs & Services”**.  
3. Click on **OAuth Consent Screen** in the left sidebar.  
4. Then click **Get Started**.

### OAuth Configuration:
- **App name**: n8n  
- **User support email**: Your email (i.e. john@gmail.com)  
- **Audience**: External  
- **Contact information**: Your email (i.e. john@gmail.com)  

Click **Continue** & **Create**.

### After OAuth Configuration:
1. Hit the hamburger helper in the top left corner.  
2. Click **“APIs & Services”**.  
3. Click **“OAuth Consent Screen”**.  
4. Click on **Audience** on the sidebar.  
5. Click on **+ Add Users** under **Test Users**.  
6. Add your email.  
7. Click **Publish App**.

## OAuth Client Settings:
1. Hit the hamburger helper in the top left corner.  
2. Click **“APIs & Services”**.  
3. Click **“OAuth Consent Screen”**.  
4. Click on **Create OAuth Client**.  
   - **Application Type**: Web Application  
   - **Name**: n8n  
   - **Authorized redirect URI**:  
     > **Note:** This is not the **Authorized JavaScript origins** + Add URI.

For cloud version, you’ll need to find your URI:  
Find this inside n8n by creating a workflow, selecting a **Google Drive node** → adding any actions (e.g., “copy file”) → **Credential to connect with** → **Create new credential** → **OAuth Redirect URL**.  
Example:  
```

[https://oauth.n8n.cloud/oauth2/callback](https://oauth.n8n.cloud/oauth2/callback)

```

For self-hosted version, you’ll need to find your URI:  
Find this inside n8n by creating a workflow, selecting a **Google Drive node** → adding any actions (e.g., “copy file”) → **Credential to connect with** → **Create new credential** → **OAuth Redirect URL**.  
Example:  
```

[https://n8n.srv43242.hstgr.cloud/rest/oauth2-credential/callback](https://n8n.srv43242.hstgr.cloud/rest/oauth2-credential/callback)

```

Paste this **OAuth Redirect URL** from n8n into **Authorized redirect URIs** in Google Cloud Console.  
Click **Create** in Google Cloud Console.

## Step 6: Authenticating Apps
1. Hit the hamburger helper in the top left corner.  
2. Click **“APIs & Services”**.  
3. Click **Credentials**.  
4. Click the **Pencil icon** (edit).  
5. Keep this page open so that you can easily reference the:  
   - **Client ID**
   - **Client secret**

6. Copy the **client ID** and **client secret**.  
7. Return back to n8n.  
   Inside n8n, create a workflow (or open an existing one), selecting a **Google Drive node** → adding any action (e.g., “copy file”) → **Credential to connect with**.  


Click **Sign In With Google**.  
Choose your account with the same email as the test user.  
Click **continue**.  
Tick all permissions and confirm.

Repeat steps 1-7 for the following APIs:  
- Gmail API  
- Google Docs API  
- Google Sheets API  
- Google Calendar API  
- Google Slides API
```

This markdown version should make it easy to format and display the guide on platforms like GitHub or other markdown readers.
