---
title: Integrating a prompt inside an iFrame in my site
excerpt: >-
  Configuration guide for triggering Recurly Engage prompts from within a child
  iFrame using the browser `postMessage` API.
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
  <div class="rp-overview">Show a Recurly Engage prompt from a button or event inside an iFrame. Your iFrame sends a message to the parent page, where the Recurly Engage software development kit (SDK) displays the prompt.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
</div>

# How can I trigger a prompt from inside an iFrame?

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Load the SDK on the parent page</h4><p>Load the Engage SDK only on your parent page, and have it listen for <code>postMessage</code> events.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Send a message from the iFrame</h4><p>In your child iFrame, send a message to the parent window. Engage intercepts it and displays the corresponding prompt.</p></div>
  </div>
</div>

Format the message as `"rf_prompt_<PROMPT_ID>"`.


<Image src="https://files.readme.io/32501c2-image.png" align="center" width="75%" border={true} />


In your iFrame’s HTML and JavaScript, attach a click handler that sends the prompt ID to the parent. Replace `66bc51c0-9829-4c4a-8697-223d0fff860a` with your own prompt ID:

```html
<button onclick="postSubmitPayment()">Submit Payment</button>

<script>
  function postSubmitPayment() {
    parent.postMessage("rf_prompt_66bc51c0-9829-4c4a-8697-223d0fff860a", "*");
  }
</script>
```

Once the SDK on the parent page receives that message, it opens the specified prompt just as if it were triggered natively. You can call `postMessage` as many times as needed, and all user interactions (accept, decline, dismiss) function normally.

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Important</strong>For cross-domain iFrames, replace <code>"*"</code> with your parent page’s origin for secure messaging.</div>
</div>
