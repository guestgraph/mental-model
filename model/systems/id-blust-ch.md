---
id: 01a17143-31aa-7ef8-813f-4a1f19056896
source: Local
kind: SaaS
owner: Owner
processor: Google Cloud
serves:
  - Answering
---

# id.blust.ch

> Signs readers in to the chat on guestgraph.io with ZITADEL, the identity service blust.ch runs at https://id.blust.ch in its Google Cloud project blust-ch-mcp in the Zurich region for the chats on blust.ch, companygraph.io and guestgraph.io, and issues the token from which the chat reads the models a reader may choose. Anyone may open an account there, at the login with their email address or by signing in with Google, Microsoft or GitHub, and the owner may also make one and send an invitation; what an account may use is a role, which only the owner grants, and a reader with no role on a site is answered there as a visitor is, by the default model and against the visitors' day share. Before an account is used, its address is verified: the login mails a code there where it is not verified yet, and an address Google, Microsoft or GitHub proved needs none. That code and the owner's invitation are id.blust.ch's mail, which goes out from no-reply@blust.ch through Gmail, signed in as a user of the owner's Google Workspace. A person who signs up with their address chooses a passkey or a password; a password sign-in also needs an authenticator app or a security key, and a password is reset through the verified address, while a sign-in with Google, Microsoft, GitHub or a passkey is never required to have a second factor. Beside ZITADEL, in the same project and region, blust.ch runs the link check, a small service of its own that ZITADEL calls after every sign-in with Google, Microsoft or GitHub: it links that account to an existing one by its address only where the provider proved the address and exactly one account holds it with its address verified, and it keeps nothing and logs no address and no token.

## Connects to

| System | As | Service | Carries | Via |
| --- | --- | --- | --- | --- |
| Sign in with Google | OpenID Connect | | | HTTPS |
| Sign in with Microsoft | OpenID Connect | | | HTTPS |
| Sign in with GitHub | OAuth 2.0 | | | HTTPS |

## References

| What | URL |
| --- | --- |
| The service's source, infrastructure and the owner's steps | https://github.com/robertblust/id-blust-ch |
