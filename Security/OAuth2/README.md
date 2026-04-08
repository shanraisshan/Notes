# OAuth2

> An authorization framework that lets a third-party app access a user's data on another service without sharing the user's password

## ELI5

Term|Analogy (Hotel)
:-:|:-:
**OAuth2**|A hotel front desk that gives out limited keycards
**Resource Owner (You)**|The hotel guest
**Client (App)**|Your friend who needs pool access
**Auth Server**|The front desk that issues keycards
**Resource Server (API)**|The hotel facilities (pool, gym)
**Access Token**|A keycard that only opens certain doors
**Refresh Token**|A pass to get a new keycard without checking in again
**Scopes**|Which doors the keycard can open
**PKCE**|A wristband that proves the keycard request is legit

## 4 Key Roles

Role|Description
:-:|:-:
**Resource Owner**|The user who owns the data
**Client**|The third-party app wanting access
**Authorization Server**|The service that issues tokens (e.g., Google's auth server)
**Resource Server**|The API holding the user's data (e.g., Google Drive API)

## Authorization Code Grant (Most Common Flow)

```
1. App redirects user to Authorization Server
2. User logs in & consents to the requested scopes
3. Auth Server redirects back to App with a short-lived Authorization Code
4. App exchanges that code (+ client_secret) for an Access Token (server-to-server)
5. App uses the Access Token to call the Resource Server (API)
6. When token expires, App uses Refresh Token to get a new one silently
```

## Key Concepts

- **Access Token** -> short-lived (minutes/hours), used to call APIs
- **Refresh Token** -> long-lived, used to get new access tokens silently
- **Scopes** -> define what the app can do (e.g., `read:email`, `write:calendar`)
- **PKCE** (Proof Key for Code Exchange) -> extra security for mobile/SPA apps where you can't safely store a `client_secret`

## Grant Types

Grant|When to use
:-:|:-:
**Authorization Code**|Server-side apps (most common)
**Authorization Code + PKCE**|Mobile apps, SPAs
**Client Credentials**|Machine-to-machine (no user involved)
**Device Code**|TVs, CLI tools (no browser on device)

## Example - Sign in with Google on LinkedIn

```
1. You tap "Sign in with Google" on LinkedIn
   -> LinkedIn sends you to accounts.google.com

2. Google asks: "LinkedIn wants to see your name, email, and profile picture"
   -> You tap "Allow"

3. Google redirects back to LinkedIn with a secret code

4. LinkedIn (server-to-server) exchanges that code with Google
   -> Google replies with an Access Token + basic info
      { name: "Shayan", email: "shayan@gmail.com", picture: "..." }

5. LinkedIn checks: "Do I already have a user with shayan@gmail.com?"
   -> Yes? Logs you in
   -> No? Creates a new account using that info

6. You're in. LinkedIn never asked you for a password.
```

### What LinkedIn CAN vs CAN'T do

CAN|CAN'T
:-:|:-:
See your name & email|Read your Gmail
See your profile picture|Access your Google Drive
Know it's really you|Change your Google password
-|See your search history

Because the **scope** was only `openid email profile`

## Example - Meme App posting to Reddit

```
1. You click "Connect with Reddit" on the Meme App
   -> Meme App sends you to reddit.com/authorize

2. Reddit asks: "Meme App wants to post on your behalf, read your subscriptions"
   -> You click "Allow"

3. Reddit redirects back to Meme App with a secret code
   -> memeapp.com/callback?code=abc123

4. Meme App (server-to-server) tells Reddit:
   "Here's the code abc123 + my app credentials"
   -> Reddit replies with an Access Token

5. Meme App uses that token to post your meme:
   -> POST reddit.com/api/submit
      Authorization: Bearer <token>

6. Token expires in 1 hour. Meme App uses a Refresh Token
   to get a new one - you never have to log in again.
```

The app **never sees your password**. It only gets a limited token that you can revoke anytime from your account settings.
