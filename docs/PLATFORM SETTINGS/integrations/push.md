---
title: Push notifications
excerpt: >-
  How to configure push notification endpoints and credentials for Recurly
  Engage.
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
          You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

Push prompts use device-specific endpoints to deliver notifications to users outside the app or website.

# Key benefits

* **Reach users off-app**: Engage users even when they aren’t actively using your site or app.
* **Highly targeted**: Deliver notifications to specific user segments based on traits and behaviors.
* **Flexible delivery**: Support FCM, ADM, and APNs channels from a single interface.

***

## Add endpoint addresses

First, upload or sync your device endpoint information to Recurly Engage via CSV or API:

1. Prepare a CSV with columns:

   1. `Id`: The device endpoint identifier.
   2. `ChannelType`: The push service (`FCM`, `ADM`, or `APNS`).
   3. `Address`: The device token.
   4. `User.UserId`: The Recurly Engage user ID.

   This can be a one-time initial load. To keep endpoints up to date:

   1. Periodically upload updated CSVs to the S3 bucket provided by Recurly Engage.
   2. Or call the Device Registration API from your application.

**Registration API**

```
POST <base_url>/ingest/update_push_endpoint
Headers:
  Rf-App: <app_slug>
  User-Id: <user_id>
  Content-Type: application/json
Body:
{
  "token": "4d5e6f1a2b3c4d5e6f7g8h9i0j1a2b3c",
  "channel_type": "GCM",
  "endpoint_id": "eqmj8wpxszeqy/b3vch04sn41yw"
}
```

### Amazon Device Messaging (ADM)

Required information: `ADM Client ID`, `ADM Client Secret`.\
Follow Amazon’s credential guide: [Obtain ADM Credentials](https://developer.amazon.com/docs/adm/obtain-credentials.html).

### Apple Push Notification Service (APNs)

**Required information:**

* `Apple Push Notifications Service Bundle ID`
* `Apple Push Notifications Service Team ID`
* `Apple Push Notifications Service Token Key`
* `Apple Push Notifications Service Token Key ID`

**Steps:**

1. Log in to [Apple Developer](https://developer.apple.com/account).
2. Under Certificates, IDs & Profiles → Identifiers, select your app to view the Bundle ID.
3. Under Membership Details, note your Team ID.
4. Under Certificates, IDs & Profiles → Keys, create or retrieve an APNs key.

### Firebase Cloud Messaging (FCM)

Required information: `FCM service JSON` key.

Steps:

1. In [Firebase Console](https://console.firebase.google.com/), go to Project Settings → Service Accounts.
2. Click **Generate New Private Key** and download the JSON file.
3. Upload this JSON in the Recurly Engage console under Settings → Integrations → Push.

```json
{
  "type": "service_account",
  "project_id": "PROJECT_ID",
  "private_key_id": "PRIVATE_KEY_ID",
  "private_key": "PRIVATE_KEY",
  "client_email": "FIREBASE_ADMIN_SDK_EMAIL",
  "client_id": "CLIENT_ID",
  "auth_uri": "https://accounts.google.com/o/oauth2/auth",
  "token_uri": "https://oauth2.googleapis.com/token",
  "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
  "client_x509_cert_url": "CLIENT_X509_CERT_URL"
}
```

### Upload file to Recurly Engage

Once you have your FCM JSON file or ADM/APNs credentials, upload them in the Recurly Engage console:

1. Go to **Settings → Integrations → Push**.
2. Select the channel and upload the corresponding credential file or enter key values.
3. Click **Save** to activate push messaging for your application.