---
title: Zendesk
excerpt: >-
  Configuration guide for the Recurly Engage Zendesk integration, enabling
  support workflows to be triggered directly from prompts. Connect via OAuth
  or a legacy API token.
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
  <div class="rp-overview">The Zendesk integration lets Recurly Engage prompts handle support tasks directly in your Zendesk instance, so common requests don't need a manual hand-off.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.</li>
  <li>For a new OAuth connection: <strong>Admin Center access</strong> in the Zendesk instance you want to connect.</li>
  <li>For a legacy API-token connection: your Zendesk account must support API token authentication, and you must have an admin-generated token.</li>
</ul>

# Definition

<div class="rp-definition">The Zendesk integration allows Recurly Engage prompts to perform support actions, such as creating tickets, assigning agents, and managing user status, directly in your Zendesk instance.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-ticket" aria-hidden="true"></i></div>
    <strong>Automate ticket creation</strong>
    <span>Instantly log support tickets when users interact with prompts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-list-check" aria-hidden="true"></i></div>
    <strong>Streamline support workflows</strong>
    <span>Assign, prioritize, or suspend users without leaving your app's interface.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-stopwatch" aria-hidden="true"></i></div>
    <strong>Improve response times</strong>
    <span>Reduce manual hand-offs by handling common support tasks programmatically.</span>
  </div>
</div>

# Key details

## Connecting via OAuth (recommended)

Recurly Engage connects to your Zendesk instance so prompts and surveys can take support actions on your behalf — for example creating a support ticket when a customer responds to a survey, assigning tickets to a group or agent, or setting ticket priority and status.

The connection uses OAuth: you approve access once, and Recurly Engage receives a secure token that can be revoked at any time. Zendesk has deprecated API-token authentication (existing API tokens stop working April 30, 2027, and new ones can no longer be created), so all new connections use OAuth.

**What you will need:**

* An admin account in the Zendesk instance you want to connect (Admin Center access)
* An admin account in Recurly Engage
* The **Redirect URL** for your Engage app, provided by your Recurly onboarding contact

### Path A — New OAuth setup

**Step 1 — Create an OAuth client in your Zendesk Admin Center**

1. Sign in to Zendesk as an admin and open **Admin Center**.
2. Go to **Apps and integrations → APIs → Zendesk API → OAuth Clients**, then click **Add OAuth client**.
3. Fill in the client details:
   * **Client name:** Recurly Engage (any name works — this is a display label)
   * **Unique identifier:** choose an identifier such as `recurly_engage` (must be unique within your Zendesk instance — you will paste this into Recurly Engage later)
   * **Redirect URL:** enter the Redirect URL provided by your Recurly contact, exactly as given (it looks like `https://sapi.redfast.com/apps/<your-app-id>/zendesk/auth`)
   * If your Zendesk shows a **Client kind** option, select **Confidential**.
   * If the form lets you restrict **Allowed scopes**, either leave scopes unrestricted or include `read` and `write`.
4. Save the client. Zendesk shows a **client secret** — copy it now and keep it handy (you will paste it into Recurly Engage in Step 2). Also note the **Unique identifier** you chose.

**Step 2 — Enter the credentials in Recurly Engage**

1. Sign in to Recurly Engage and go to **Settings → Connectors → Zendesk**.
2. Enter your Zendesk **domain** (for example, `yourcompany.zendesk.com`).
3. Paste the OAuth client's **Unique identifier** into **OAuth Client ID** and the **client secret** into **OAuth Client Secret**.
4. Click **Save**.

**Step 3 — Connect and approve**

1. In the same dialog, click **Connect with Zendesk**.
2. You will be redirected to your Zendesk instance to approve access. Review the permissions and click **Allow** (or **Approve**).
3. You are returned to Recurly Engage with a confirmation message.

**Step 4 — Verify**

* Reopen **Settings → Connectors → Zendesk**: the dialog shows a **Connected via Zendesk OAuth** confirmation.
* Zendesk connector actions (for example **Create Ticket**) are now available when configuring prompt actions.

### Path B — Existing connections using a shared API token

If your Zendesk connection was previously set up by sharing an API token with Recurly:

1. Open **Settings → Connectors → Zendesk** and confirm your Zendesk domain is saved (your existing username and API key are already stored).
2. Click **Connect with Zendesk** and approve access on your Zendesk instance.

Recurly Engage registers the OAuth client in your Zendesk automatically — no Admin Center setup is required on your side. We recommend completing this before **April 30, 2027**, when Zendesk API tokens stop working. Once the OAuth connection is active, you can clear the stored API key from the dialog.

## Legacy connection settings (API token)

> Zendesk has deprecated API tokens: new tokens can no longer be created, and existing tokens stop working **April 30, 2027**. New connections should use the OAuth flow above.

Provide the following settings (existing connections only):

* **Domain**: Your Zendesk domain (for example, `yourcompany.zendesk.com`).
* **API Key** (also called an API token): Your Zendesk API token.
* **Username**: Your Zendesk account email.

## Supported actions

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>User dependencies</td><td>Additional instructions</td></tr>
  <tr><td>Create support ticket with notification of offer acceptance</td><td>Creates a support ticket with information about the user and prompt</td><td>n/a</td><td>—</td></tr>
  <tr><td>Set priority of all existing tickets</td><td>Sets priority attribute for all tickets created by the user</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>Select the priority level on the prompt screen</td></tr>
  <tr><td>Assign all existing tickets to a specific agent</td><td>Assigns all tickets created by the user to one agent</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>Select the agent on the prompt screen. Manage agents under <strong>Admin &gt; People &gt; Agents</strong> in Zendesk dashboard</td></tr>
  <tr><td>Suspend user</td><td>Sets the user to suspended state</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>—</td></tr>
  <tr><td>Restore suspended user</td><td>Restores the user from suspended state</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>—</td></tr>
  <tr><td>Assign all existing tickets to a group</td><td>Assigns all tickets created by the user to a group</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>Select the group on the prompt screen. Manage groups under <strong>Admin &gt; People &gt; Groups</strong> in Zendesk dashboard</td></tr>
  <tr><td>Delete all tickets</td><td>Deletes all tickets created by the user</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>—</td></tr>
  <tr><td>Set status of all existing tickets</td><td>Sets status of all tickets created by the user</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>Select the status on the prompt screen</td></tr>
  <tr><td>Delete and spam all existing tickets</td><td>Marks all tickets created by the user as spam</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>—</td></tr>
</table>

## Managing or removing access

<ul class="rp-list">
  <li>To disconnect from the Recurly Engage side: open <strong>Settings → Connectors → Zendesk</strong>, turn off the connection and clear the saved OAuth client credentials, then click <strong>Save</strong>.</li>
  <li>To revoke access from the Zendesk side: <strong>Admin Center → Apps and integrations → APIs → Zendesk API → OAuth Clients</strong> → select the Recurly Engage client and revoke it.</li>
  <li>Disconnecting keeps the OAuth client registration, so you can reconnect later without repeating the setup.</li>
</ul>

## Troubleshooting

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Message / symptom</td><td>Cause and fix</td></tr>
  <tr><td>"Invalid or expired OAuth state" after approving</td><td>The connection attempt timed out (valid for 10 minutes). Click <strong>Connect with Zendesk</strong> again and approve promptly.</td></tr>
  <tr><td>Zendesk shows an error about the redirect URL</td><td>The Redirect URL registered on the OAuth client must match the URL provided by Recurly exactly, including <code>https://</code> and the path. Re-copy it from your Recurly contact.</td></tr>
  <tr><td>"Zendesk OAuth client is not registered"</td><td>The client identifier and secret were not saved in the Connectors dialog before clicking Connect. Complete Step 2 of Path A.</td></tr>
  <tr><td>Dialog shows the connection as expired</td><td>The OAuth token could not be refreshed (e.g. the client was revoked in Zendesk). Re-click <strong>Connect with Zendesk</strong> to re-authorize.</td></tr>
  <tr><td>Connected, but ticket actions fail</td><td>Confirm the authorizing user has the Zendesk permissions the actions require (e.g. agent/admin rights to create tickets).</td></tr>
</table>

## Security notes

<ul class="rp-list">
  <li>Recurly Engage acts on your Zendesk instance through an OAuth token scoped to <code>read</code> and <code>write</code> on your Zendesk API, with a refresh token so the connection stays active without repeated approvals.</li>
  <li>Tokens are stored encrypted in Recurly's secrets infrastructure and are never displayed in the product.</li>
  <li>You can revoke access at any time from either side (see <em>Managing or removing access</em> above); revoking immediately stops all Recurly Engage Zendesk actions.</li>
</ul>

## Additional resources

<ul class="rp-list">
  <li><a href="https://support.zendesk.com/hc/en-us/articles/4408845965210-Using-OAuth-authentication-with-your-application" target="_blank">Using OAuth authentication with your application (Zendesk)</a></li>
  <li><a href="https://support.zendesk.com/hc/en-us/articles/226022787-Generating-a-new-API-token-" target="_blank">Zendesk API token</a></li>
</ul>
