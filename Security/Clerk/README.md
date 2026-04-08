# Clerk

> A drop-in authentication and user management platform for web apps that handles sign-up, sign-in, OAuth2, sessions, and pre-built UI components

## ELI5

Term|Analogy (Hotel)
:-:|:-:
**Clerk**|A full-service reception desk you hire instead of building your own
**Sign in with Google**|Clerk handles calling Google and getting guest info for you
**Pre-built UI components**|Ready-made check-in kiosks you just plug in
**Session management**|The reception desk tracking who's checked in and when to log them out
**User management dashboard**|A back-office screen showing all guests and their details
**Organizations**|Group bookings where one person manages the whole team
**MFA**|A second ID check before handing over the room key

## What Clerk Does

- **Sign up / Sign in** -> email, password, social logins (Google, GitHub, etc.), magic links, OTP
- **OAuth2 / OpenID Connect** -> handles the full flow under the hood
- **User management** -> profile pages, session handling, multi-factor auth (MFA)
- **Organization management** -> teams, roles, permissions
- **Pre-built UI components** -> `<SignIn />`, `<UserButton />`, `<UserProfile />` for React/Next.js
- **Session & JWT handling** -> manages tokens, refresh, and middleware for protected routes

## How It Relates to OAuth2

Clerk **uses** [OAuth2](../OAuth2) internally. When a user clicks "Sign in with Google", Clerk handles the entire OAuth2 flow (redirect to Google, get the code, exchange for token, fetch user info). You just configure your Google credentials in the Clerk dashboard.

## Comparison

-|Build Yourself|Clerk|Firebase Auth
:-:|:-:|:-:|:-:
**Effort**|High|Very low|Low
**UI**|Build from scratch|Pre-built components|Pre-built (FirebaseUI)
**User management dashboard**|Build it|Included|Firebase Console
**Pricing**|Free (your time)|Free tier, then paid per MAU|Free tier, then paid
**Framework support**|Whatever you build|Next.js, React, Remix, etc.|Most platforms

## Links

Description|Link
:-:|:-:
Clerk official site|https://clerk.com
Clerk docs|https://clerk.com/docs
