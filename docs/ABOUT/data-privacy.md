---
title: Data privacy and security
excerpt: >-
  Overview of Recurly Engage’s data privacy and security practices, ensuring
  compliance and user trust.
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

Recurly Engage processes only the data you designate, with strict controls around retention, and access—providing a secure, privacy-first engagement platform.

# Definition

The **Data Privacy & Security** section outlines how Recurly Engage handles end-user information, including what is collected, how it is stored, and how it is protected.

# Key benefits

* **Privacy-by-design**: Minimal default data collection with configurable tracking to meet your privacy requirements.
* **Regulatory compliance**: Built-in support for SOC 2 Type II, GDPR, and CCPA controls to safeguard user data.
* **Flexible retention**: Default 90-day lookback window with optional extended retention or suppression lists.

# Key details

By default, Recurly Engage does not collect or process end-user information besides session timestamps. IP addresses are never stored. Tracking is limited to the attributes and events you explicitly enable. Data is retained for a default 90-day lookback window, configurable per your needs.

## IP Address

Recurly Engage never stores end-user IP addresses. Location targeting uses a one-way hashed integration with a locally hosted copy of MaxMind’s GeoIP database. IP data remains internal and is not shared externally.

## Cookies

Recurly Engage does not utilize cookies in its platform operations unless you explicitly enable first-party cookies for your use case.

## Email address

Recurly Engage does not use email addresses by default. **Email addresses may only be imported at your option** as a custom trait (see [User Traits](user-traits)). Third-party connectors (e.g., SendGrid) may require encrypted email for campaign triggers.

## End user privacy

We never share your end-user data with third parties nor aggregate external data against your user profiles. We rely on platform-recommended identifiers (e.g., IDFV on iOS, Instance ID on Android) and never use hardware or network identifiers (MAC, IP) for identification.

## SOC 2 Type II

Recurly Engage is SOC 2 Type II compliant, audited by a trusted AICPA firm. Controls cover security policies, change management, access controls, backup, disaster recovery, and incident response. Growth and Enterprise customers can request the SOC 2 report via their Customer Success Manager.

## GDPR / CCPA compliance

See the Recurly Engage [Privacy Policy](https://www.redfast.com/privacy) for details on GDPR and CCPA adherence, data subject requests, and privacy rights.

## Suppression list

You may provide a list of user IDs to suppress. Recurly Engage will immediately cease processing any data associated with those users.

## Data retention

Data is retained no longer than 90 days past the user’s last activity by default. Extended lookback (up to one