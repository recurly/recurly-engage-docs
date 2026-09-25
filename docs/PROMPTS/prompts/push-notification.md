---
title: Push prompts
excerpt: >-
  Details on creating and managing push notifications (Push Prompts) in Recurly
  Engage.
deprecated: false
hidden: false
metadata:
  title: ''
  description: >
    A guide to Recurly Engage's push notifications feature. It explains how to
    set up, configure, and send scheduled push prompts to users' devices through
    various channels.
  robots: index
next:
  description: ''
---
<div class="rp-page">
<div class="rp-overview">Push Prompts deliver scheduled notifications straight to your users' devices—even when they're not in your app. Set up your channel credentials, sync device tokens, and build a segment to target exactly who should receive each message, all from Recurly Engage.</div>
<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> May not be included in all plans — contact <a href="https://recurly.com/demo/contact-sales/" target="_blank">Recurly Sales</a> to discuss upgrade options</div>
<div class="rp-toc">
<a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
<a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
<a class="rp-toc-pill" href="#step-by-step-guide"><span class="rp-toc-num">3</span>Step-by-step guide</a>
</div>
</div>

### Prerequisites

<ul class="rp-list">
<li>Company, App Administrator, or App Member permissions in Recurly Engage.</li>
</ul>


<Image src="https://files.readme.io/f00d61d6a8654389878ce3c4e673366ed89c0e2737c9267a0e1e34ea29fc1b9e-Screenshot_2025-09-12_at_10.39.42_AM.png" align="center" width="40%" border={true} />



<Image src="https://files.readme.io/889186a4e41b9748da8d5504b1d6bcf7dd69e716510249b668073852f4c39c13-Screenshot_2025-09-12_at_10.39.52_AM.png" align="center" width="40%" border={true} />


# Definition

<div class="rp-definition">Push Prompts send scheduled notifications directly to your users' devices, even when they aren't actively using your app. Recurly Engage delivers these messages through supported channels, including Amazon Device Messaging (ADM), Apple Push Notifications service (APNs), and Firebase Cloud Messaging (FCM).</div>

# Key benefits

<div class="rp-benefits">
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Direct engagement</strong><span>Reach users on their devices with timely messages, increasing re-engagement.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Scheduled delivery</strong><span>Plan notifications in advance to hit optimal send times.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Multi-channel support</strong><span>Send via Amazon Device Messaging, Apple Push Notifications service, or Firebase Cloud Messaging.</span></div>
</div>

# Step-by-step guide

Before you begin, make sure you're an active Recurly Engage member on a plan that includes Push Prompts. If you're not, <a href="https://recurly.com/product/engage/" target="_blank">book a demo today</a>.

<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">1</div><div><h4>Set up credentials</h4><p>Add credentials for the push channels you want to use.</p></div></div>
</div>

<ol>
<li>In the Recurly Engage management console, Pulse, navigate to <strong>Settings → Integrations → Push Notifications</strong>.</li>
<li>Enter credentials for the desired <a href="https://docs.recurly.com/recurly-engage/docs/push" target="_blank">Push channels</a>.</li>
</ol>


<Image src="https://files.readme.io/dea5d335047a382b0ccca5259e5aa5e2df5a3d28cd4ea9373c278ad1275486af-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">2</div><div><h4>Sync device tokens</h4><p>Configure and upload device tokens so Recurly Engage can target your users' registered devices.</p></div></div>
</div>

<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">3</div><div><h4>Create a custom device</h4><p>Set up a <a href="https://docs.recurly.com/recurly-engage/docs/custom-devices" target="_blank">custom device</a> profile for push targeting.</p></div></div>
</div>

<ol>
<li>In Pulse, navigate to <strong>Settings → Custom Devices</strong>.</li>
<li>Select <strong>+ New Custom Device</strong>.</li>
</ol>

<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">4</div><div><h4>Create a Push Segment</h4><p>Build a <a href="https://docs.recurly.com/recurly-engage/docs/segments" target="_blank">segment</a> to target your push audience.</p></div></div>
</div>

<ol>
<li>In Pulse, navigate to the <strong>Segments</strong> section and select <strong>+ New Segment</strong>.</li>
<li>Select <strong>Push notification</strong> as the device type.</li>
<li>Configure your segment with the appropriate settings, including channel type.</li>
</ol>


<Image src="https://files.readme.io/e6d0bd51758f313b517af9c708b667b1e90e2b44737178f8d7c1952f80d6a5e3-Push_2.png" align="center" width="75%" border={true} />


<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">5</div><div><h4>Create a Push prompt</h4><p>Build the <a href="https://docs.recurly.com/recurly-engage/docs/prompts" target="_blank">prompt</a> that will deliver the notification.</p></div></div>
</div>

<ol>
<li>In Pulse, navigate to the Prompts section and select <strong>+ New Prompt</strong>.</li>
<li>Select <strong>Custom</strong> for the Device Type and <strong>Push Device</strong> for the device type, then choose the <strong>Push</strong> prompt style.</li>
</ol>


<Image src="https://files.readme.io/b7baff81edc13a1eccf215d64894cb6ff4743a64a5d45f388bc9f8daeca6ab95-Push_3.png" align="center" width="75%" border={true} />


<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">6</div><div><h4>Configure the prompt</h4><p>Set the segment, schedule, and design for your push notification.</p></div></div>
</div>

<ul class="rp-list">
<li><strong>Segment</strong>: choose the Push Notification segment to target specific users.</li>
<li><strong>Schedule</strong>: set the times your prompt will send.</li>
</ul>

<ol>
<li><strong>Customizable timing</strong>: set specific start and end dates and times for your scheduled push notification.</li>
<li><strong>Quiet times</strong>: establish periods during which notifications should not be sent, preventing disruptions.</li>
<li><strong>Local time zones</strong>: configure the task to run according to the user's local time zone, ensuring accurate timing regardless of location.</li>
</ol>

<ul class="rp-list">
<li><strong>Design</strong>: edit the prompt design to customize messaging, imagery, and actions.</li>
</ul>


<Image src="https://files.readme.io/3240e7cf7e9fc9d27b5b10c7301fdcfcf7a1a3df6f11ea11144115478ce95e86-Push_4.png" align="center" width="75%" border={true} />


<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">7</div><div><h4>Save and schedule</h4><p>Once everything's configured, select <strong>Save</strong> and <strong>Schedule</strong> to deliver your push notifications to your audience.</p></div></div>
</div>
