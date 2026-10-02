---
title: Website
excerpt: >-
  How to configure and use Website Actions within Recurly Engage, including
  adding simple built-in actions and custom JavaScript code.
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
  <div class="rp-overview">Send users where you want them to go, or run your own code, when they interact with a Recurly Engage prompt. Website actions cover simple jobs like redirects and new tabs, and custom JavaScript for everything else.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#add-a-simple-action"><span class="rp-toc-num">2</span>Add a simple action</a>
    <a class="rp-toc-pill" href="#add-custom-javascript-code"><span class="rp-toc-num">3</span>Add custom JavaScript code</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <span style={{fontWeight: "bold"}}>Company</span> or <span style={{fontWeight: "bold"}}>App Administrator</span> permissions in Engage.</li>
</ul>

# Definition

<div class="rp-definition">Website actions let Engage call custom client-side code, optionally passing information from form inputs.</div>

# Add a simple action

Several simple actions are available, such as redirecting to a new URL or opening a URL in a new tab. For example, to add a website action that opens a new tab with a specific URL:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Add a website action</h4><p>From the prompt detail page, add a new website action.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select the action type</h4><p>Select <span style={{fontWeight: "bold"}}>Open URL on New Tab</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add the action</h4><p>Click <span style={{fontWeight: "bold"}}>Add action</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Edit the action</h4><p>Click the edit (pencil) icon.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Add the URL argument</h4><p>Add a new argument with <code>key=url</code> and a value equal to the link you want to take the user to.</p></div>
  </div>
</div>

# Add custom JavaScript code

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Website Actions</h4><p>Go to <span style={{fontWeight: "bold"}}>Settings → Actions → Website Actions</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/9e361b2-Screenshot_2024-04-30_at_22.47.54.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Create a website action</h4><p>Specify the name of the action and write the code. See <a href="/docs/forms" target="_blank">form inputs</a> for more information on accessing user input.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/2272dcc-Screenshot_2024-04-30_at_22.51.56.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Save your changes</h4><p>Save the changes.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/a30b0cb-Screenshot_2024-04-30_at_22.53.42.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Select your prompt</h4><p>Go to <span style={{fontWeight: "bold"}}>Prompts</span> and select your prompt.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/6354038-Screenshot_2024-04-30_at_22.55.04.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Add the website action</h4><p>Add the website action to the prompt.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/1928bd0-Screenshot_2024-05-01_at_21.30.27.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/921f4c4-Screenshot_2024-05-01_at_21.31.29.png" align="center" width="75%" border={true} />
