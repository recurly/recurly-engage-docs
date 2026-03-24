---
title: Hightouch
excerpt: >-
  Learn how to connect your data warehouse to Recurly Engage using Hightouch’s
  HTTP Request destination to automate user property updates and
  personalizations.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide provides a step-by-step walkthrough for syncing your customer data from Hightouch to Recurly Engage. By utilizing the Recurly Engage Ingest API, you can ensure your application has the most up-to-date user attributes—such as subscription plans, names, and custom tags—triggering more relevant user experiences and retention workflows.

# Key benefits

* **Automated Personalization:** Keep user properties in Recurly Engage perfectly in sync with your source of truth (Snowflake, BigQuery, etc.) without manual uploads.
* **Low-Code Integration:** Use Hightouch’s flexible HTTP Request destination to connect to the Recurly Engage API without needing custom engineering resources.
* **Real-Time Accuracy:** Ensure that changes in a user’s status (e.g., upgrading from "Basic" to "Premium") are reflected immediately in your engagement campaigns.

# Key steps

## Step one: Create a New Destination 


In your Hightouch dashboard, navigate to the Destinations page and click Add Destination. Search for and select HTTP Request.

<Image align="center" src="https://files.readme.io/f9ca3e5af1bb3580c1d1eb1a31dd739b33e39bd82039fa9dca9b45699bfcb00f-1.png" />

## Step two: Configure the HTTP Request

<Image align="center" src="https://files.readme.io/b6b9a73bb04adbdb16cd81547747ed4909c1b4a33f258973f74c259a408c4067-2.png" />

To establish the connection, enter the following configuration details:

* **Authentication Method:** Select Basic Auth.
* **Base URL:**`https://conduit.redfast.com/ingest/property`
* **HTTP Headers:** Add a header for your App ID:
  * **Key:** `Rf-App`
  * **Value:** `<YOUR_APP_ID>` (Replace this with your specific Recurly Engage App ID).  

<Image align="center" src="https://files.readme.io/564f1cf153749242eee8b3872cfa0651b991adb13041a7bca71e69b6abe90eb6-3.png" />

## Step three: Initialize a New Sync

Navigate to the Syncs page and click Add Sync. Select the Model containing the user data you wish to move into Recurly Engage.

<Image align="center" src="https://files.readme.io/29efb9e046de6d47e36385b6196da2de554d6c66bb91c05f0e898158061ccbf2-4.png" />

## Step four: Select the Destination

Choose the HTTP Request destination you configured in Step 2.

<Image align="center" src="https://files.readme.io/f8633c34562976a7d27af39f84fabe4d319981f9ee6e815ddec5e9616faf9e62-5.png" />

## Step five: Configure Sync Mapping

While specific mapping depends on your data model, use these standard configurations for the payload:

<br />

| Setting      | Configuration                                   |
| :----------- | :---------------------------------------------- |
| Batching     | A single row                                    |
| HTTP Method  | POST                                            |
| URL          | Leave blank (it will inherit from the Base URL) |
| Payload Type | JSON                                            |

<br />

## Step six: Map the Request Body

Ensure your JSON payload matches the Recurly Engage requirements. Your mapping should generate a structure similar to this:

```
{
  "id": "123-456-789-012-",
  "user_id": "test-user-001",
  "properties": {
    "email": "user@example.com",
    "first_name": "Jane",
    "last_name": "Doe",
    "plan": "premium"
  }
}

```

**Example response** 

```
{
  "success": true
}

```

<br />

Note: The id field in the JSON body must match the App ID used in your HTTP headers.

<Image align="center" src="https://files.readme.io/4189f595130811d944706d105c1364987eb2972d93b30102111769e78d015760-6.png" />

<br />
