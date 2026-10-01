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
<div class="rp-page">
  <div class="rp-overview">Stop downloading and uploading CSV files by hand. Schedule a daily Looker export and it pushes your user traits straight into the Recurly Engage Amazon S3 bucket, where Engage picks them up automatically.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <span style={{fontWeight: "bold"}}>Company</span> or <span style={{fontWeight: "bold"}}>App Administrator</span> permissions in Engage.</li>
  <li>A Looker account with access to the dashboard containing your user traits.</li>
  <li>Amazon Web Services (AWS) S3 credentials retrieved from Engage (Pulse) for secure uploads.</li>
</ul>

# Definition

<div class="rp-definition">A scheduled Looker export delivers a CSV file of your user traits to the Engage S3 bucket on a set schedule.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Automated workflows</strong>
    <span>Eliminate manual CSV downloads by scheduling daily Looker exports directly into S3.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Consistent data</strong>
    <span>Ensure your trait imports always use the latest data without human intervention.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Secure transfer</strong>
    <span>Engage manages the credentials, and they only grant access to the designated S3 bucket.</span>
  </div>
</div>

# Key details

Follow these steps to configure your Looker schedule and connect it to your Engage S3 bucket:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Retrieve S3 credentials in Pulse</h4><p>Go to <span style={{fontWeight: "bold"}}>Settings &gt; Custom Traits</span> in your Engage console.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/c23d4a0-settings-integrations.png" align="center" width="75%" border={true} />


Click **Click here for AWS S3 credentials** and check **Show Credentials** to reveal your Bucket name, Access Key, and Secret Key.


<Image src="https://files.readme.io/3ab86ef-settings-aws-modal.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/7b8d41a-aws-settings-1.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Log in to Looker</h4><p>Open a new browser tab and go to <a href="https://looker.com/login" target="_blank">Looker</a>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/a91f5e4-looker-1.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Locate your user data Look</h4><p>Select the folder containing your user trait data.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/2d62fee-looker-2.png" align="center" width="75%" border={true} />


Choose an existing Look that outputs all required trait columns.


<Image src="https://files.readme.io/7d73497-looker-3.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Ensure correct column ordering</h4><p>Make sure the first column is your customer ID (for example, <code>user_id</code>). If it isn't, edit the Look to reposition it.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/844acc0-looker-4a.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Create a schedule</h4><p>Click <span style={{fontWeight: "bold"}}>Create Schedules</span> on the Look.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/90c9d44-looker-4.png" align="center" width="75%" border={true} />


In the schedule modal, choose **Amazon S3**, then paste your Engage Bucket, Access Key, and Secret Key into the fields. Adjust the delivery time if needed.


<Image src="https://files.readme.io/d2a0178-looker-5.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Save and verify</h4><p>Save the schedule. Looker now pushes a CSV of your user traits to the S3 bucket each day at the scheduled time.</p></div>
  </div>
</div>

Once you've set this up, Engage automatically ingests the daily CSV upload within a few hours, keeping your user traits up to date for segmentation and targeting.
