---
title: User traits
excerpt: >-
  This article explains how to import, configure, and manage custom user traits
  in Recurly Engage to extend targeting beyond default behavior metrics.
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

Recurly Engage user traits let you import and define custom attributes — such as lifetime value, satisfaction score, or subscription dates — so you can target users on more than built-in behavior metrics. You can bring these traits in as a scheduled CSV batch, through a partner integration, or in real time by calling the Ingest API directly. Once a trait lands in Engage, it's available for segmentation and personalized prompts.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2"></i>
          You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2"></i>
          For CSV ingest: access to your Engage S3 bucket or a CSV export source.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2"></i>
          For real‑time ingest via the Ingest API: your App ID and API Key (<strong>Settings &gt; Application &gt; API Key</strong>).
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4"></i>
          For third‑party connector activation, ensure required ID columns are present.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4"></i>
          CSV uploads to S3 are ingested within a few hours — for real‑time updates, use the Ingest API.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

**User traits** are custom attributes imported into Recurly Engage that extend targeting beyond built-in usage metrics. You can ingest them three ways: a scheduled CSV upload to a secure S3 bucket, a partner integration, or a direct call to the Ingest API for real-time updates.

# Key benefits

- **Richer personalization**: Leverage lifetime value, plan type, NPS, or any business metric in your prompts.
- **Ingest at the speed you need:** Batch data through CSV, or push it in real time through the Ingest API when freshness matters.
- **Flexible integrations**: Activate push notifications and connector‑based traits for services like Stripe, Salesforce, SendGrid, and Zendesk.

# Key details

- **CSV format**: First column must be `user_id`, additional columns become traits.
- **Trait types**: Number, string, boolean, date with corresponding display options (slider, multi‑select, date range).
- **Push endpoints**: Import device tokens via CSV or Device Registration API.
- **3rd‑party requirements**: Specific ID or email columns needed for connectors (e.g., `stripe_id`, `email_address`).

You can import additional user traits into Recurly Engage to give you greater ability to target users based on characteristics beyond site/app usage. Typical examples are lifetime value, customer satisfaction score, subscription start date, renewal date etc. User traits can be added via a CSV file. This file will be stored, encrypted, on a secured S3 bucket and will be ingested within a few hours of uploading. Each column will be mapped into a Recurly Engage user trait.

You can also export your CSV data from [Looker](looker).

# Choosing an Ingest Method

Recurly Engage supports three ways to get custom trait data in. Pick the one that matches how fresh your data needs to be and where it lives.

| Method              | Latency            | Best for                                           |
| ------------------- | ------------------ | -------------------------------------------------- |
| CSV upload to S3    | Within a few hours | Bulk or historical loads, scheduled exports        |
| Partner integration | Varies by partner  | Data already flowing through a supported connector |
| Ingest API          | Real time          | Custom data from your own backend or database      |

## Method 1 — CSV upload to S3 (batch)

You can import user traits into Recurly Engage to target users on characteristics beyond site or app usage. Typical examples are lifetime value, customer satisfaction score, subscription start date, and renewal date. User traits can be added via a CSV file. This file is stored, encrypted, on a secured S3 bucket and is ingested within a few hours of uploading. Each column is mapped into a Recurly Engage user trait.

You can also export your CSV data from Looker.

### Formatting the CSV file

Here is an example of what your CSV file should look like. **The first column must be**`user_id`, all other columns can be utilized to specify user traits. There are no limits on columns but please keep in mind this can significantly impact load and sync times.

```csv
user_id,ltv,channel,signup_date,nps,plan_type,payment_failed
789129,150,adwords,2011-08-12,8,monthly,false
322321,0,blog,2014-09-18,7,trial,false
900194,100,homepage,2018-04-01,9,annual,true
```

### Required columns for third party connectors

**Note**: To activate third‑party connectors like Stripe, Salesforce, and others the following columns are required:

- **Salesforce**: `salesforce_id` (the id of the Salesforce contact) OR `email_address`
- **SendGrid**: `email_address`
- **Stripe**: `stripe_id` (the id of the Stripe customer) OR `email_address`
- **Zendesk**: `zendesk_id` (the id of the Zendesk user) OR `email_address`

### Push Notifications

To activate push notifications, the following columns are required:

1. `Id`: the id of the device (aka endpoint)
2. `ChannelType`: the push channel of this endpoint. Allowed values: `FCM`, `ADM`, `APNS`
3. `Address`: The device token
4. `User.UserId`: the id of the user. This should be the same id that Recurly Engage uses

This CSV can be used as a one‑time initial load of endpoint information. To keep this information updated, you may:

1. Upload an updated CSV periodically into your S3 bucket from Recurly Engage OR
2. Call the [Device Registration](ref:device-registration) API with the device token from your client application

### Upload the file to AWS

After creating your CSV file you will need to upload it to your secure area on Amazon S3. In this step we will retrieve the credentials to allow you to upload the file.

1. Go to **Settings > User Traits**


   <Image src="https://files.readme.io/da8ce5e-image.png" align="center" border={true} />


2. Select "Click here for AWS S3 credentials"


   <Image src="https://files.readme.io/679abbc-image.png" align="center" border={true} />


3. Check the **Show Credentials** box to view your credentials. You will need to use the AWS Bucket, Access Key and Secret Key to login and securely upload via AWS. Keep this information handy, you will need it to upload the CSV.

4. If you are automating a file transmission to the S3 bucket, use the above credentials with the AWS SDK or CLI ([link](https://aws.amazon.com/cli/)). Otherwise, the following steps describe how to manually upload a CSV file.

5. Download [Cyberduck](https://cyberduck.io/download/). Cyberduck is a client that you can connect to AWS with. Otherwise the next steps describe how to use a free S3 client to upload the CSV file.

6. Click the plus sign to add a new connection


   <Image src="https://files.readme.io/fc1bd26-image.png" align="center" border={true} />


7. Select **Amazon S3** from the dropdown list


   <Image src="https://files.readme.io/193d845-image.png" align="center" border={true} />


8. Type in your credentials. Then click **More Options** and type in your AWS Bucket in the **Path** field with the "/" in front of it (see the screenshot for reference)


   <Image src="https://files.readme.io/5a75d55-image.png" align="center" border={true} />


9. Locate **Upload Location** which gives you the location where you should put your CSV.


   <Image src="https://files.readme.io/db565a6-image.png" align="center" border={true} />


10. Drag and drop your CSV file to the **ingest** folder, using the information from above. Within 3 hours your data will be fully ingested. You should receive an email once you’re done.


    <Image src="https://files.readme.io/5319ecd-image.png" align="center" border={true} />


## Method 2 — Partner integrations

If your data already lives in a supported tool — such as Segment, Stripe, Braze, or Salesforce — you can sync traits by connecting that tool directly, without preparing and uploading a CSV yourself. Set the integration up in Pulse (Engage Backend) and trait updates propagate into Engage on their own. Latency depends on the partner; for example, Segment traits typically appear within minutes. See CRM integrations for the full list and setup steps.

**Note:** This is different from the connector column requirements under Method 1. Use Method 1 when you're uploading a CSV that feeds a connector; use this method when the connector syncs to Engage on its own.

## Method 3 — Ingest API (real time)

When your data lives in your own backend or internal database — or you simply need updates faster than the batch cycle allows — call the Ingest API directly. There's no S3 upload and no batch wait; traits are available as soon as the call succeeds.&#x20;

- **Endpoint:** POST [https://conduit.redfast.com/ingest/property](https://conduit.redfast.com/ingest/property)
- **Authentication:** Basic Auth with your Application ID and API Key. Depending on your client, the API Key may be passed as a query-string parameter. Find your API Key at Settings > Application > API Key.
- **Payload:**

  <br />

  ```
  {
    "id": "123-456-789-012-",
    "user_id": "test-user-001",
    "properties": {
      "first_name": "Jane",
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

Each key in properties maps to a Recurly Engage user trait. As with CSV ingest, you'll configure the type and display for each new trait before using it in a segment (see Customizing user traits).

**Note:** This section covers custom attribute (property) data. To send event or behavioral signals — for example, "payment failed" or "user hit a milestone" — see Usage tracking.

# Customizing User Traits

After a trait is ingested — whether by CSV, a partner integration, or the Ingest API — you'll need to configure it before you can use it in your segments.

1. Go to **Settings > User Traits**, you should now see all imported columns


   <Image src="https://files.readme.io/1fe2677-image.png" align="center" border={true} />


2. Now go through each trait to update the type, display and description (optional) by clicking on the **Edit** (pencil) icon


   <Image src="https://files.readme.io/669873a-image.png" align="center" border={true} />



   <Image src="https://files.readme.io/56498d9-image.png" align="center" border={true} />


   This may seem intimidating at first but let’s take a look at the original CSV to see what the values should be:

   ```csv
   user_id,ltv,channel,signup_date,nps,plan_type,payment_failed
   789129,150,adwords,2011-08-12,8,monthly,false
   322321,0,blog,2014-09-18,7,trial,false
   900194,100,homepage,2018-04-01,9,annual,true
   ```

   - **ltv** – number
   - **channel** – string
   - **signup_date** – date
   - **nps** – number
   - **plan_type** – string
   - **payment_failed** – boolean

   Now that we know the types, selecting the display is easy. Here are some guidelines for display options:

   - **numbers** – slider (unless it refers to an ID such as `zendesk_id`, then multi‑select)
   - **string** – multi‑select
   - **boolean** – multi‑select
   - **date** – date_range


   <Image src="https://files.readme.io/e418514-image.png" align="center" border={true} />


   **Note**: For the slider display type there is a **Normalize to 0–10** checkbox. You can check this box and it will allow you to target percentiles rather than the exact number (e.g. top 20% LTV users).


   <Image src="https://files.readme.io/b56371d-image.png" align="center" border={true} />


3. Now when you create or edit a segment you can filter based on these user traits.


   <Image src="https://files.readme.io/0cc29c7-image.png" align="center" border={true} />


<br />

<br />
