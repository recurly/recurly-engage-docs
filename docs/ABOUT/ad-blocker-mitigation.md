---
title: Adblocker mitigation
excerpt: >-
  Configuration guide for Ad Blocker Mitigation, enabling Recurly Engage to
  function when users have ad blockers enabled.
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

Public reports ([Backlinko](https://backlinko.com/ad-blockers-users), [Statista](https://www.statista.com/topics/3201/ad-blocking/#topicOverview)) indicate up to 50% of web users employ ad blockers, which may block third-party JavaScript tags—including Recurly Engage’s—disabling engagement prompts.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          You must be on the Enterprise plan or have purchased the Ad Blocker Mitigation add-on.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

**Ad Blocker Mitigation** routes the Recurly Engage tag and API traffic through a customer-owned subdomain (e.g., `track.yourcompany.com`) so that browser extensions no longer block prompt delivery. The change requires only a DNS update and reconfiguration of your tag manager.

# Key benefits

* **Maximized reach**: Ensure prompts reach users even when ad blockers are enabled.
* **DNS-only setup**: No code changes—just configure a CNAME and update your script tag.
* **Seamless updates**: Recurly Engage continues to host and update SDK assets on the new subdomain.

# Key details

To enable Ad Blocker Mitigation, complete the following steps:

## Update DNS

1. **Agree upon** a subdomain (e.g., `track.yourcompany.com`).
2. Your Recurly Engage Customer Success Manager will provide the CNAME target (e.g., `yourapp.redcurlyengage.com`).
3. Your IT team adds a CNAME entry in your DNS: