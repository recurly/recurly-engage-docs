---
title: Looker
excerpt: >-
  The Looker integration lets you schedule daily exports of CSV user trait data
  directly from Looker into your Recurly Engage AWS S3 bucket for seamless
  ingestion.
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
        <p>
          <i className="fa-solid fa-check mr-2" />
          A Looker account with access to the dashboard containing your user traits.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          AWS S3 credentials retrieved from Recurly Engage (pulse) for secure uploads.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

Configures a scheduled Looker data export to push CSV files of user traits into the Recurly Engage S3 bucket.

# Key benefits

* **Automated workflows**: Eliminate manual CSV downloads by scheduling daily Looker exports directly into S3.
* **Consistent data**: Ensure your trait imports always use the latest data without human intervention.
* **Secure transfer**: Credentials are managed by Recurly Engage and only grant access to the designated S3 bucket.

# Key details

Below is a step-by-step guide to configure your Looker schedules and connect them to your Recurly Engage S3 bucket.

1. **Retrieve S3 credentials in Pulse**

   * **Go** to **Settings > Custom Traits** in your Recurly Engage console.

   <br />

   <Image align="center" className="border" border={true} width="700px" src="https://files.readme.io/c23d4a0-settings-integrations.png" />

   * Click **Click here for AWS S3 credentials** and check **Show Credentials** to reveal your Bucket name, Access Key, and Secret Key.

   <br />

   <Image align="center" className="border" border={true} width="700px" src="https://files.readme.io/3ab86ef-settings-aws-modal.png" />

   <Image align="center" className="border" border={true} width="700px" src="https://files.readme.io/7b8d41a-aws-settings-1.png" />

2. **Log in to Looker**

   * Open a new browser tab and navigate to [Looker](https://looker.com/login).

   <br />

   <Image align="center" className="border" border={true} width="700px" src="https://files.readme.io/a91f5e4-looker-1.png" />

3. **Locate your user data Look**

   * Select the folder containing your user trait data.

   <br />

   <Image align="center" className="border" border={true} width="700px" src="https://files.readme.io/2d62fee-looker-2.png" />

   * Choose an existing Look that outputs all required trait columns.

   <br />

   <Image align="center" className="border" border={true} width="700px" src="https://files.readme.io/7d73497-looker-3.png" />

4. **Ensure correct column ordering**

   * Make sure the first column is your customer ID (e.g., `user_id`). If not, edit the Look to reposition it.

   <br />

   <Image align="center" className="border" border={true} width="700px" src="https://files.readme.io/844acc0-looker-4a.png" />

5. **Create a schedule**

   * Click **Create Schedules** on the Look.

   <br />

   <Image align="center" className="border" border={true} width="700px" src="https://files.readme.io/90c9d44-looker-4.png" />

   * In the schedule modal, choose **Amazon S3**, then paste your Recurly Engage Bucket, Access Key, and Secret Key into the fields. Adjust the delivery time if needed.

   <br />

   <Image align="center" className="border" border={true} width="700px" src="https://files.readme.io/d2a0178-looker-5.png" />

6. **Save and verify**

   * Save the schedule. Looker will now push a CSV of your user traits to the S3 bucket each day at the scheduled time.

Once set up, your Recurly Engage instance will automatically ingest the daily CSV upload within a few hours, keeping your user traits up to date for segmentation and targeting purposes.