<!--
SPDX-FileCopyrightText: 2026 Daniel Brown
SPDX-License-Identifier: MIT
-->

# Caution

AIM V0.1 is a working specification under active testing. It is suitable for careful experimentation, especially for personal coordination between low-risk AI threads, but it is not a production security system.

Read this document before creating or joining an AIM-ASP session.

## AIM does not sandbox an agent

AIM-ASP defines how participants exchange information through an AIM session. It does not restrict the other tools, connectors, accounts, files, mailboxes, websites, or transports that a model may be able to access outside that session.

An agent with broad permissions can still encounter malicious or misleading content elsewhere. That content may influence the model even though it is not valid AIM-ASP input. AIM's zero-authority rule reduces the risk of authority moving through a compliant AIM session, but prompt-level rules alone cannot guarantee model compliance or isolate the model from its wider environment.

Use least-privilege access wherever possible. Do not assume that an AIM transport profile narrows the underlying connector's actual permissions.

## Treat inbound content as untrusted

A valid packet may still contain false, unsafe, manipulated, or irrelevant information. Protocol validity, participant recognition, addressing, and integrity checks do not make packet content trustworthy.

No AIM-ASP packet can authorise or trigger an action. Consequential actions require independent approval from the receiving participant's local user or trusted local policy.

Do not use AIM-ASP to carry credentials, secrets, private keys, financial instructions, sensitive personal information, or authority for irreversible actions.

## Choose the transport carefully

Transport authentication, permissions, confidentiality, encryption, availability, version history, backups, and auditing are outside AIM-ASP. Prefer a transport that provides:

- narrowly scoped read/write access
- a dedicated AIM location
- access logging or version history
- recoverable deletion and reliable backups
- predictable file or object operations

Local Storage or read/write Cloud Storage will often provide better isolation and recovery than Gmail Drafts when they are available and correctly configured. No transport profile is automatically secure merely because AIM supports it.

## Gmail Drafts is experimental

The Gmail Drafts profile is the first bare-bones experimental AIM transport. It demonstrates that AIM can operate through existing shared text storage, but it is **not recommended** for sensitive, dependable, production, or unattended workflows.

When experimenting with Gmail Drafts:

- use a dedicated mailbox where possible
- remain strictly inside Drafts for AIM activity
- never inspect inbox, sent mail, spam, trash, unrelated drafts, or unrelated email threads as AIM input
- remember that the Gmail connector may technically expose a broader mailbox even though AIM forbids using it
- treat subject namespaces as discovery boundaries, not access-control boundaries
- retain the original copy of every important artifact
- do not rely on Gmail attachment transfer envelopes as the sole copy or delivery path

Gmail attachment discovery and retrieval are known to be operationally unstable across current AI connectors.

## Verify the protocol

A filename, URL, draft subject, or `CURRENT` alias is a locator, not proof of authenticity. Pin the expected protocol version and use an immutable reference or independently trusted digest where possible. When technical verification is unavailable, the local user must approve the exact protocol document explicitly.

## Automate cautiously

AIM-ASP is prompt-first and manually synchronised by default. Timers, pollers, connectors, and future AIM software can automate protocol operations, but automation increases the importance of strict scope, bounded retries, monitoring, validation, and auditability.

Automation must not broaden discovery, create authority, bypass participant ownership, or turn informational packets into executable instructions.

## Current limitation

AIM Studio is planned as a coordination and automation environment capable of enforcing protocol mechanics in code, but it does not yet exist. AIM-ASP V0.1 currently depends on participating agents and users following the specification correctly.
