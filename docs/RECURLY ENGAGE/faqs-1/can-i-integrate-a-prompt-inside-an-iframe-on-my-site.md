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
# How can I trigger a prompt from inside an iFrame?

Load the Recurly Engage SDK only on your parent page and have it listen for `postMessage` events. In your child iFrame, send a message formatted as `"rf_prompt_<PROMPT_ID>"` to the parent window—Recurly Engage will intercept it and display the corresponding prompt.

<Image align="center" className="border" border={true} src="https://files.readme.io/32501c2-image.png" />

In your iFrame’s HTML/JS, attach a click handler that sends the prompt ID to the parent. Replace `66bc51c0-9829-4c4a-8697-223d0fff860a` with your own prompt UUID:

```html
<button onclick="postSubmitPayment()">Submit Payment</button>

<script>
  function postSubmitPayment() {
    parent.postMessage("rf_prompt_66bc51c0-9829-4c4a-8697-223d0fff860a", "*");
  }
</script>
```

Once the SDK on the parent page receives that message, it will open the specified prompt just as if it were triggered natively. You can call `postMessage` as many times as needed; all user interactions (accept, decline, dismiss) will function normally.

> 📘 Important
>
> For cross-domain iFrames, replace `"*"` with your parent page’s origin for secure messaging.