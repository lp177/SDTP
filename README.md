<p align="center"><img src="logo.svg" alt="SDTP: Sequential Document Transfer Protocol" width="720"></p>

# SDTP: Sequential Document Transfer Protocol

**A mailbox protocol for AI agents.** Agents (coding assistants in terminals, CI bots, scripts) hand each other tasks, questions and answers through mailboxes. A small relay keeps each mailbox as an ordered sequence. Every document is taken by exactly one reader, exactly once, and nothing is lost because a terminal closed.

This repository specifies the **exchange itself**, with its security layer deliberately left out so that it can be understood, tried on one computer and implemented in an afternoon:

- 📬 **Mailboxes as sequences**: append, list, take once, consume.
- 🛟 **Take-once delivery**: concurrent readers race safely, and a reader that dies never causes a double execution.
- 🏠 **Machine and session mailboxes**: documents left for a silent session are relayed to its computer, where another session picks them up.
- 📣 **Ephemeral channels**: broadcasts to every session of a computer or of a network, read by all, consumed by none, gone in a minute.
- 🔌 **Several relays per mailbox**: automatic negotiation of the fastest shared one.
- 🗂️ **Backlog**: yesterday's task never runs on its own today.

➡️ **Read the specification: [SDTP.md](SDTP.md)**

## SDTP and SDTPS

SDTP is the clear-text profile, for learning, testing and single-user setups on one computer. Anywhere else, use **SDTPS**, the secure profile: key-pair identities, signed requests, end-to-end encrypted and signed documents, pairing by a one-time code, and an operator console. It is specified at **[github.com/lp177/SDTPS](https://github.com/lp177/SDTPS)**.

Every SDTPS implementation is an SDTP implementation with the security layer added.

## Status

Informational draft, version 1, describing a protocol in production use between AI agent sessions. Issues and independent implementations are welcome.

## License

Licensed under the [Apache License, Version 2.0](LICENSE).
