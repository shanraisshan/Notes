# WorkOS

> An authentication and identity platform focused on enterprise features like SSO, Directory Sync, and admin portals for B2B apps

## ELI5

Term|Analogy (Hotel)
:-:|:-:
**WorkOS**|A reception desk that specializes in corporate group bookings
**SSO**|Accepting company badges instead of making each employee check in separately
**Directory Sync (SCIM)**|Auto-syncing the guest list from the company's HR system
**Admin Portal**|A self-serve kiosk where the company's IT admin manages their group booking
**AuthKit**|A basic check-in desk for individual guests (email, password, social login)
**Organizations**|Separate group bookings for different companies

## What WorkOS Does

- **SSO (Single Sign-On)** -> connect to enterprise identity providers (Okta, Azure AD, OneLogin)
- **Directory Sync (SCIM)** -> auto-sync users/groups from a company's HR system
- **Admin Portal** -> self-serve UI for IT admins to configure [SSO](../SSO) themselves
- **AuthKit** -> drop-in auth (email, password, social login, MFA) similar to [Clerk](../Clerk)
- **Organizations** -> multi-tenant support for B2B apps
- **Fine-grained authorization (FGA)** -> role and permission management

## Clerk vs WorkOS

-|Clerk|WorkOS
:-:|:-:|:-:
**Target**|B2C and general apps|B2B / enterprise apps
**Strength**|Beautiful drop-in UI, fast setup|SSO, SCIM, enterprise compliance
**SSO**|Paid add-on|Core feature
**Directory Sync**|Limited|Core feature (SCIM)
**Pre-built UI**|Rich components|AuthKit (simpler)
**Use case**|"I need login for my SaaS"|"My customer's IT team needs Okta SSO"
**Pricing**|Per MAU|Per connection

## When to Use

- Building a **consumer app** or early-stage SaaS -> [Clerk](../Clerk)
- Your customers are **enterprises** asking for SSO and SCIM -> **WorkOS**

## Links

Description|Link
:-:|:-:
WorkOS official site|https://workos.com
WorkOS docs|https://workos.com/docs
