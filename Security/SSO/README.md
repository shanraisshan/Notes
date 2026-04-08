# SSO (Single Sign-On)

> An authentication mechanism that lets a user log in once and access multiple apps without signing in to each separately

## ELI5

Term|Analogy (Waterpark)
:-:|:-:
**SSO**|A wristband you get at the gate — scan once, ride everything all day
**Identity Provider (Okta, Azure AD)**|The gate where you get your wristband
**Service Provider (Slack, Jira)**|The rides that scan your wristband
**SAML Assertion**|The barcode on your wristband that proves you scanned in
**Session**|How long your wristband is valid before you need to scan again

## How It Works

```
1. Employee opens Slack
   → Slack says "I don't know who you are, go to your company's Okta"

2. Okta asks the employee to log in (or recognizes an existing session)
   → Employee logs in once

3. Okta sends a signed assertion back to Slack
   → "This is Shayan, he's verified, let him in"

4. Slack logs the employee in

5. Employee opens Jira
   → Jira says "go to Okta"
   → Okta already has a session — no login needed
   → Okta sends assertion to Jira
   → Jira logs the employee in automatically
```

## SSO vs OAuth2

-|SSO|OAuth2
:-:|:-:|:-:
**Purpose**|One login for many apps|Grant third-party apps limited access to your data
**Who it's for**|Employees in an organization|Users on the internet
**Problem it solves**|"I don't want to log into 15 apps every morning"|"I want this app to post to my Reddit without giving it my password"
**Who controls it**|IT admin (company-wide)|The user (per-app consent)
**Protocol**|SAML, OpenID Connect|OAuth2
**Tokens**|Session/assertion (proves "who you are")|Access token (proves "what you can do")

## How SSO and OAuth2 Relate

They are **not competitors** — they often work together. SSO can use OpenID Connect (built on [OAuth2](../OAuth2)) under the hood.

- **OAuth2** = **Authorization** -> "what are you allowed to do?"
- **SSO** = **Authentication** -> "who are you?" (asked once, trusted everywhere)

## Common SSO Protocols

Protocol|Description
:-:|:-:
**SAML 2.0**|XML-based, older, widely used in enterprises
**OpenID Connect (OIDC)**|Built on OAuth2, JSON-based, modern
**WS-Federation**|Microsoft-centric, used with ADFS

## Common Identity Providers

Provider|Description
:-:|:-:
**Okta**|Popular enterprise identity provider
**Azure AD (Entra ID)**|Microsoft's identity platform
**OneLogin**|Cloud-based identity management
**Google Workspace**|Google's enterprise identity
