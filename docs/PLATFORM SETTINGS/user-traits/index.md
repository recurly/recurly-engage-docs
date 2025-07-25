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

Recurly Engage User Traits let you import and define custom attributes—such as lifetime value, satisfaction score, or subscription dates—via CSV or third‑party connectors. Once configured, these traits become available for segmentation and personalized prompts.

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
        <p>
          <i className="fa-solid fa-check mr-2" />
          Access to an S3 bucket or CSV export source.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          For third‑party connector activation, ensure required ID columns are present.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

**User Traits** are custom attributes imported into Recurly Engage that extend targeting capabilities beyond built‑in usage metrics. Traits are ingested via secure CSV uploads to S3 or synchronized through partner integrations.

# Key benefits

* **Richer personalization**: Leverage lifetime value, plan type, NPS, or any business metric in your prompts.
* **Seamless sync**: Encrypted CSV ingestion with AWS S3 credentials for secure, automated uploads.
* **Flexible integrations**: Activate push notifications and connector‑based traits for services like Stripe, Salesforce, SendGrid, and Zendesk.

# Key details

* **CSV format**: First column must be `user_id`, additional columns become traits.
* **Trait types**: Number, string, boolean, date with corresponding display options (slider, multi‑select, date range).
* **Push endpoints**: Import device tokens via CSV or Device Registration API.
* **3rd‑party requirements**: Specific ID or email columns needed for connectors (e.g., `stripe_id`, `email_address`).

You can import additional user traits into Recurly Engage to give you greater ability to target users based on characteristics beyond site/app usage. Typical examples are lifetime value, customer satisfaction score, subscription start date, renewal date etc. User traits can be added via a CSV file. This file will be stored, encrypted, on a secured S3 bucket and will be ingested within a few hours of uploading. Each column will be mapped into a Recurly Engage user trait.

You can also export your CSV data from [Looker](looker).

## Formatting the CSV file

Here is an example of what your CSV file should look like. **The first column must be`user_id`**, all other columns can be utilized to specify user traits. There are no limits on columns but please keep in mind this can significantly impact load and sync times.

```csv
user_id,ltv,channel,signup_date,nps,plan_type,payment_failed
789129,150,adwords,2011-08-12,8,monthly,false
322321,0,blog,2014-09-18,7,trial,false
900194,100,homepage,2018-04-01,9,annual,true
```

### 3rd Party Integrations

**Note**: To activate third‑party connectors like Stripe, Salesforce, and others the following columns are required:

* **Salesforce**: `salesforce_id` (the id of the Salesforce contact) OR `email_address`
* **SendGrid**: `email_address`
* **Stripe**: `stripe_id` (the id of the Stripe customer) OR `email_address`
* **Zendesk**: `zendesk_id` (the id of the Zendesk user) OR `email_address`

### Push Notifications

To activate push notifications, the following columns are required:

1. `Id`: the id of the device (aka endpoint)
2. `ChannelType`: the push channel of this endpoint. Allowed values: `FCM`, `ADM`, `APNS`
3. `Address`: The device token
4. `User.UserId`: the id of the user. This should be the same id that Recurly Engage uses

This CSV can be used as a one‑time initial load of endpoint information. To keep this information updated, you may:

1. Upload an updated CSV periodically into your S3 bucket from Recurly Engage OR
2. Call the [Device Registration](ref:device-registration) API with the device token from your client application

## Upload the file to AWS

After creating your CSV file you will need to upload it to your secure area on Amazon S3. In this step we will retrieve the credentials to allow you to upload the file.

1. Go to **Settings > User Traits**

   <Image align="center" className="border" border={true} src="https://files.readme.io/da8ce5e-image.png" />

2. Select "Click here for AWS S3 credentials"

   <Image align="center" className="border" border={true} src="https://files.readme.io/679abbc-image.png" />

3. Check the **Show Credentials** box to view your credentials. You will need to use the AWS Bucket, Access Key and Secret Key to login and securely upload via AWS. Keep this information handy, you will need it to upload the CSV.

4. If you are automating a file transmission to the S3 bucket, use the above credentials with the AWS SDK or CLI ([link](https://aws.amazon.com/cli/)). Otherwise, the following steps describe how to manually upload a CSV file.

5. Download [Cyberduck](https://cyberduck.io/download/). Cyberduck is a client that you can connect to AWS with. Otherwise the next steps describe how to use a free S3 client to upload the CSV file.

6. Click the plus sign to add a new connection

   <Image align="center" className="border" border={true} src="https://files.readme.io/fc1bd26-image.png" />

7. Select **Amazon S3** from the dropdown list

   <Image align="center" className="border" border={true} src="https://files.readme.io/193d845-image.png" />

8. Type in your credentials. Then click **More Options** and type in your AWS Bucket in the **Path** field with the "/" in front of it (see the screenshot for reference)

   <Image align="center" className="border" border={true} src="https://files.readme.io/5a75d55-image.png" />

9. Locate **Upload Location** which gives you the location where you should put your CSV.

   <br />

   <Image align="center" className="border" border={true} src="https://files.readme.io/db565a6-image.png" />

10. Drag and drop your CSV file to the **ingest** folder, using the information from above. Within 3 hours your data will be fully ingested. You should receive an email once you’re done.

    <Image align="center" className="border" border={true} src="https://files.readme.io/5319ecd-image.png" />

## Customizing User Traits

After importing the CSV successfully you will need to configure the new user traits before you can use them in your Segments.

1. Go to **Settings > User Traits**, you should now see all imported columns

   <Image align="center" className="border" border={true} src="https://files.readme.io/1fe2677-image.png" />

2. Now go through each trait to update the type, display and description (optional) by clicking on the **Edit** (pencil) icon

   <br />

   <Image align="center" className="border" border={true} src="https://files.readme.io/669873a-image.png" />

   <br />

   <Image align="center" className="border" border={true} src="https://files.readme.io/56498d9-image.png" />

   This may seem intimidating at first but let’s take a look at the original CSV to see what the values should be:

   ```csv
   user_id,ltv,channel,signup_date,nps,plan_type,payment_failed
   789129,150,adwords,2011-08-12,8,monthly,false
   322321,0,blog,2014-09-18,7,trial,false
   900194,100,homepage,2018-04-01,9,annual,true
   ```

   * **ltv** – number
   * **channel** – string
   * **signup\_date** – date
   * **nps** – number
   * **plan\_type** – string
   * **payment\_failed** – boolean

   Now that we know the types, selecting the display is easy. Here are some guidelines for display options:

   * **numbers** – slider (unless it refers to an ID such as `zendesk_id`, then multi‑select)
   * **string** – multi‑select
   * **boolean** – multi‑select
   * **date** – date\_range

   <Image align="center" className="border" border={true} src="https://files.readme.io/e418514-image.png" />

   **Note**: For the slider display type there is a **Normalize to 0–10** checkbox. You can check this box and it will allow you to target percentiles rather than the exact number (e.g. top 20% LTV users).

   <Image align="center" className="border" border={true} src="https://files.readme.io/b56371d-image.png" />

3. Now when you create or edit a segment you can filter based on these user traits.

   <Image align="center" className="border" border={true} src="https://files.readme.io/0cc29c7-image.png" />

   <br />