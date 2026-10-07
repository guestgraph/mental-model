---
id: 01a1128e-e26e-7286-afbe-3de101a5f56e
source: Local
decided: 2026-10-06
kind: Data protection
status: Standing
by: Owner
---

# The Claude account we build GuestGraph on keeps model training off

> The Claude account on which the Owner and the agents specify, build and review GuestGraph has “Help improve our AI models” switched off, so Anthropic does not use those chats and coding sessions to train or improve its models, the ones that work on guest identity data or a connector among them; Anthropic still processes every request under its own terms.

## The question

Anthropic's consumer terms let the holder of a Claude account choose whether its chats and coding sessions, Claude Code's among them, may be used to train and improve Anthropic's models, and Anthropic keeps a session longer when they may. GuestGraph is specified, built and reviewed in sessions on one such account, and some of those sessions read the engine's handling of guest identity data and the connectors' code. Which way the setting stands on that account is a call about who receives what our work contains, and the model did not record it.

## Alternatives

| Option | Why not |
| --- | --- |
| Leave the setting on | Every chat and coding session on the account could be used to train Anthropic's models, the ones that touch guest identity data or a connector among them, and Anthropic would keep them longer than it otherwise does. |
| Separate accounts, with the setting off only on the one used for guest identity data and connectors | Which account a session runs in would decide what Anthropic may train on, and a session that starts in a specification and ends in a connector's code would have to change accounts at a line nobody watches for. |

## Why

One setting on the one account draws the line for every session, so what Anthropic may train on does not depend on anyone sorting a session before it starts. Leaving it on would give Anthropic training data and give GuestGraph nothing it builds with.

## Consequences

Every session that specifies, builds or reviews GuestGraph runs on an account with the setting off, and what is given up is those sessions as a contribution to Anthropic's models. What the call does not change is that Anthropic still receives and processes every request under its own terms, keeps what it keeps for as long as those terms say, and under them may still use a conversation its safety review flags, and feedback sent with the thumbs buttons, to improve its models. The call is about the account the work is built on, not the chat, whose requests reach Anthropic through its API under the commercial terms the model's Anthropic page cites. The call stays right for as long as the setting stays off on every account GuestGraph is built on and Anthropic's terms keep a session out of training while it is off; it is weighed again if those terms change.

## References

| What | URL |
| --- | --- |
| Anthropic on when consumer chats and coding sessions are used for training | https://privacy.claude.com/en/articles/10023580-is-my-data-used-for-model-training |
| Anthropic's update to its consumer terms that introduced the setting | https://www.anthropic.com/news/updates-to-our-consumer-terms |
| Anthropic's consumer terms | https://www.anthropic.com/legal/consumer-terms |
