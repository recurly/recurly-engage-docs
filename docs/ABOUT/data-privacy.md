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

On an ongoing basis, Redfast will retain end-user usage data no longer than ninety days past the latest activity encountered by that end user unless extended lookback has been enabled. For customers who request the extended lookback feature, data is retained for one year. For end users that have been added to the Suppression List, Redfast will not retain any history of the end user's usage.

## API access

Any direct integration with third party systems that you configure within Redfast should be secured with a developer specific API key assigned to Redfast. Redfast uses publicly or privately supplied documentation with these APIs to establish communications between the systems. An alternative to API access for 1-Click actions is redirecting the user to an existing screen within your app to perform the desired action. However this will come with an adverse impact to conversion rate.

## Apple AppStore

In December 2020, Apple introduced new requirements for app developers to outline their apps' data collection and usage policy. The following specifies data collected by Redfast.

Data collected by default:

* **Identifiers:** Redfast does not create a user identifier. A User ID created by your system is passed on to the Redfast SDK. Please note that your system may be using Apple's IDFV identifier and passing that to the Redfast SDK. Consult with your engineer for specific details.
* **Usage Data:** Session related information. Optionally, additional user events that you elect to be tracked using Redfast.
