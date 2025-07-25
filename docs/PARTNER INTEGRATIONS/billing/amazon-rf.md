---
title: Google
excerpt: >-
  Setup guide for Google’s Firebase Cloud Messaging (FCM) connector in Recurly
  Engage Push Prompts.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          App must integrate the Recurly Engage SDK on the target platform.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Supported on Android devices and web browsers with FCM support.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **FCM** connector ingests your Firebase service account JSON and enables Recurly Engage to send push notifications via Google’s FCM infrastructure.

# Key benefits

* **Broad device reach**: Target Android apps and modern web clients.
* **Secure authentication**: Leverage Google’s service account keys.
* **Centralized management**: Handle push credentials within Recurly Engage.

# Key details

### Firebase Cloud Messaging (FCM)

**Required information:** `FCM service json` file

**Steps to obtain your FCM service JSON:**

1. **Go** to the [Firebase Console](https://console.firebase.google.com/) and **select** your project.
2. **Click** the gear icon in the sidebar and **choose** **Project Settings** → **Service Accounts**.
3. **Click** **Generate new private key**.
4. **Download** the resulting JSON file.

**Sample service account JSON payload:**

```json
{
  "type": "service_account",
  "project_id": "PROJECT_ID",
  "private_key_id": "PRIVATE_KEY_ID",
  "private_key": "-----BEGIN PRIVATE KEY-----\n...\n-----END PRIVATE KEY-----\n",
  "client_email": "firebase-adminsdk-xxx@PROJECT_ID.iam.gserviceaccount.com",
  "client_id": "CLIENT_ID",
  "auth_uri": "https://accounts.google.com/o/oauth2/auth",
  "token_uri": "https://oauth2.googleapis.com/token",
  "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
  "client_x509_cert_url": "CLIENT_X509_CERT_URL"
}
```

### Upload file to Recurly Engage

1. In Recurly Engage, **go** to **Settings** → **Push Credentials**.
2. **Select** **Firebase Cloud Messaging** and **upload** your downloaded JSON file.
3. **Toggle** **Active** to **On** to enable FCM push prompts.