---
title: Partner APIs
excerpt: >-
  How to provision and manage tenants and users programmatically via the Recurly
  Engage Partner Provisioning API.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Required plan

This feature is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* You must have **Company**, **App Administrator** or **App member** permissions in Recurly Engage.
* Partner code and shared secrets provided by Recurly Engage Partnerships.
* RSA key pair for JWT user provisioning.

# Definition

The **Partner Provisioning API** enables partners to create, retrieve, update, and manage Recurly Engage tenants and perform just-in-time (JIT) user provisioning with seamless single sign-on.

# Key benefits

* **Automate tenant setup**: Create and configure new Recurly Engage tenants via API, eliminating manual onboarding steps.
* **Just-in-time user provisioning**: Provision users and obtain session tokens on demand, enabling embedded partner portals.
* **Secure integration**: Authenticate API calls with partner-specific shared secrets and RSA-signed JWTs.

# Key details

## Introduction

The Provisioning API allows for the creation and modification of a Recurly Engage tenant via server-side integration with partners. It also supports just-in-time (JIT) user provisioning and redirects users into `pulse.recurlyengage.com` with a logged-in session. Please work with your Partnership Manager if you require access to this API.

## Endpoint info

**Base URL**: `https://<subdomain>.recurlyengage.com`

# Get tenant

Retrieve an existing tenant by its external partner ID.

## Endpoint

**GET /v1/tenants/\<external\_tenant\_id>**

## Headers

* **Content-Type**: `application/json`
* **rf-secret**: Shared secret provided by Recurly Engage (test and production secrets differ)

## Query params

* **partner\_code**: Partner Code assigned by Recurly Engage

## Response

```json
{
  "success": true,
  "external_tenant_id": "<external_tenant_id>",
  "app_id": "<app_id>",
  "tag_url": "https://<app_id>.recurlyengage.com/assets/recurly_engage.js",
  "user_first_name": "John",
  "user_last_name": "Smith",
  "user_email": "jsmith@myemail.com",
  "app_name": "My App",
  "company_name": "My Company",
  "app_domain": "myco.com",
  "test_mode": false,
  "jwt_public_key_updated_at": "2025-02-18T17:02:26.000Z"
}
```

***

## Create tenant

Create a new tenant in Recurly Engage.

## Endpoint

**POST /v1/tenants**

## Headers

* **Content-Type**: `application/json`
* **rf-secret**: Shared secret provided by Recurly Engage

## Body

All fields are required:

```json
{
  "company_name": "My Company",
  "external_tenant_id": "<external_tenant_id>",
  "app_name": "My App",
  "app_domain": "myco.com",
  "user_email": "jsmith@myemail.com",
  "user_first_name": "John",
  "user_last_name": "Smith",
  "partner_code": "<partner_code>",
  "api_key": "<integration_api_key>",
  "jwt_public_key": "-----BEGIN PUBLIC KEY-----\n..."
}
```

## Response

```json
{
  "success": true,
  "status": "provisioning_started",
  "external_tenant_id": "<external_tenant_id>",
  "app_id": "<app_id>",
  "tag_url": "https://<app_id>.recurlyengage.com/assets/recurly_engage.js",
  "test_mode": false,
  "jwt_public_key": "-----BEGIN PUBLIC KEY-----\n...",
  "jwt_public_key_updated_at": "2025-02-18T17:02:26.000Z"
}
```

## Update tenant

Modify an existing tenant’s configuration.

## Endpoint

**PATCH /v1/tenants**

## Headers

* **Content-Type**: `application/json`
* **rf-secret**: Shared secret provided by Recurly Engage

## Body

```json
{
  "external_tenant_id": "<external_tenant_id>",
  "partner_code": "<partner_code>",
  "app_domain": "myco.com",             // optional
  "api_key": "<new_integration_api_key>",// optional
  "jwt_public_key": "-----BEGIN PUBLIC KEY-----\n..." // optional
}
```

## Response

```json
{
  "success": true,
  "status": "updated",
  "external_tenant_id": "<external_tenant_id>",
  "app_id": "<app_id>",
  "tag_url": "https://<app_id>.recurlyengage.com/assets/recurly_engage.js",
  "test_mode": false,
  "jwt_public_key": "-----BEGIN PUBLIC KEY-----\n...",
  "jwt_public_key_updated_at": "2025-02-18T17:02:26.000Z"
}
```

## User provisioning and session token

Provision or retrieve a user session with a signed JWT. JIT provisions new users.

## Endpoint

**POST /v1/jwt\_session**

## Body

```json
{
  "jwt_token": "<signed_jwt>"
}
```

### JWT Payload Example

```json
{
  "sub": "<partner_user_id>",
  "external_tenant_id": "<external_tenant_id>",
  "app_id": "<app_id>",
  "role": "admin",           // "admin" or "member"
  "exp": 1712800000,
  "iat": 1712796400,
  "iss": "<partner_code>",
  "email": "jsmith@myemail.com",
  "first_name": "John",
  "last_name": "Smith"
}
```

## Response

```json
{
  "success": true,
  "external_tenant_id": "<external_tenant_id>",
  "session_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "session_token_expires_at": "2025-02-18T17:02:26.000Z"
}
```

## User redirect

Redirect an end user to Pulse with an active session.

## Endpoint

**GET /v1/session/redirect**

## Query params

* **session\_token**: JWT session token
* **redirect\_url**: (optional) relative path in Pulse, defaults to `/`

**Response**: HTTP redirect to `pulse.recurlyengage.com` (or login if invalid token)

## Testing and error responses

Use Test vs Production `rf-secret` to simulate or perform live provisioning. Standard HTTP codes apply:

* **200 OK** – Success
* **401 Unauthorized** – Invalid `rf-secret`
* **404 Not Found** – Tenant or user not found
* **409 Conflict** – Tenant already provisioned
* **422 Unprocessable Entity** – Missing/invalid fields
* **5xx** – Server error

Error payloads include `success: false` and `status` fields indicating the failure reason.