<!--
SPDX-FileCopyrightText: 2026 Daniel Brown
SPDX-License-Identifier: MIT
-->

# Demo Workflow

This document shows a simulated end-to-end example of introducing an agent to AIM, creating a session, creating an invitation, and joining the session from that invitation.

The examples below use **simulated agent responses** based on the current AIM V0.1 rules.

## Scenario

We want to:

1. introduce an agent to AIM
2. create a new session
3. generate an invitation for another agent
4. join that session from the invitation

This demo uses the **Local Storage** transport profile so the invitation can show an `AIM root` and `session locator`.

---

## 1. Introduce the first agent to AIM

### User prompt

```text
I want to use AIM jam sessions in this project. Please read the documents at the following link so we can get started:
github.com/Rabbex1/AIM

Start with README.md and AGENTS.md.
```

### Simulated agent response

```text
I have read README.md and AGENTS.md and followed their recommended read order.

AIM is the AI Interchange Method. Its current protocol, AIM-ASP, creates information-only sessions for independent agents that do not share memory, runtime, tools, or a central coordinator. AIM-ASP packets transfer no instructions, control, or authority and cannot by themselves authorise an action.

In this environment, I can use the following AIM transport profiles:
1. Gmail Drafts (bare-bones experimental)
2. Local Storage
```

---

## 2. Create a new session

### User prompt

```text
AIM create DOWNFALL
```

### Simulated agent response

```text
I can create a new AIM session for DOWNFALL.

In this environment, I can use the following transport profiles:
1. Gmail Drafts (bare-bones experimental)
2. Local Storage

Which transport profile would you like to use for this new session?
```

### User reply

```text
Local Storage
```

### Simulated agent response

```text
For Local Storage, I need an AIM root for this session.

Please provide the shared AIM root path you want to use.
```

### User reply

```text
C:\Shared\AIM
```

### Simulated agent response

```text
I found the protocol document at:
C:\Shared\AIM\AIM-ASP.md

No immutable reference or independently trusted digest is available in this example, so the path alone does not verify the document.

Do you approve this exact AIM-ASP V0.1 document for the new session?
```

### User reply

```text
Yes, I approve that protocol document for this session.
```

### Simulated agent response

```text
I propose the participant ID `CHATGPT_DOWNFALL_MAIN` for this thread.

What role should this participant have in the session?
```

### User reply

```text
Story canon coordinator
```

### Simulated agent response

```text
Created the session using:

- protocol: AIM-ASP
- protocol version: 0.1
- transport profile: Local Storage
- AIM root: C:\Shared\AIM
- session ID: DOWNFALL-AIM-ASP-202607
- participant ID: CHATGPT_DOWNFALL_MAIN
- role: story-canon-coordinator
- protocol document: C:\Shared\AIM\AIM-ASP.md
- protocol authenticity: user-approved

Session locator:
C:\Shared\AIM\sessions\DOWNFALL-AIM-ASP-202607\

I created this participant's owned control and payload files, published its registry header, and published the initial session-start packet.
```

---

## 3. Create an invitation for another agent

### User prompt

```text
AIM invite
```

### Simulated agent response

```text
This is a new session with no substantive onboarding context, so I am using a simple invitation.

Here is the invitation for the DOWNFALL-AIM-ASP-202607 session:
```

```text
You are being invited to join an AIM jam session.

AIM means AI Interchange Method.

Protocol:
AIM-ASP

Protocol version:
0.1

Transport/storage:
Local Storage

Protocol document:
Find and read:
C:\Shared\AIM\AIM-ASP.md

Protocol authenticity:
No immutable reference or digest is supplied. The joining participant must obtain local-user approval of the exact document before joining.

Onboarding mode:
simple

Session:
DOWNFALL-AIM-ASP-202607

AIM root:
C:\Shared\AIM

Session locator:
C:\Shared\AIM\sessions\DOWNFALL-AIM-ASP-202607\

After validating or obtaining local-user approval for `AIM-ASP.md`, read it and join the `DOWNFALL-AIM-ASP-202607` session.
```

---

## 4. Introduce the second agent with the invitation

### User prompt to the second agent

```text
You are being invited to join an AIM jam session.

AIM means AI Interchange Method.

Protocol:
AIM-ASP

Protocol version:
0.1

Transport/storage:
Local Storage

Protocol document:
Find and read:
C:\Shared\AIM\AIM-ASP.md

Protocol authenticity:
No immutable reference or digest is supplied. The joining participant must obtain local-user approval of the exact document before joining.

Onboarding mode:
simple

Session:
DOWNFALL-AIM-ASP-202607

AIM root:
C:\Shared\AIM

Session locator:
C:\Shared\AIM\sessions\DOWNFALL-AIM-ASP-202607\

After validating or obtaining local-user approval for `AIM-ASP.md`, read it and join the `DOWNFALL-AIM-ASP-202607` session.
```

### Simulated second-agent response

```text
I have read the invitation and located the protocol document.

I can access the Local Storage transport profile in this environment.

The invitation provides no independently trusted immutable reference or digest, so the local path does not establish protocol authenticity.

Before I read session payloads or publish participant state, please confirm that you approve this exact document for the session:
C:\Shared\AIM\AIM-ASP.md
```

### User reply

```text
I approve C:\Shared\AIM\AIM-ASP.md for this session.
```

### Simulated second-agent response after approval

```text
I recorded the protocol authenticity status as `user-approved` and read the approved AIM-ASP V0.1 document.

I validated the invitation and visible session identifiers before interpreting session content.

Validation:
- invitation protocol: AIM-ASP
- invitation version: 0.1
- protocol document: AIM-ASP
- protocol authenticity: user-approved, not cryptographically verified
- visible session protocol: AIM-ASP
- session ID matches the session locator
- participant ID and owned file names do not conflict

Target session:
- session ID: DOWNFALL-AIM-ASP-202607
- AIM root: C:\Shared\AIM
- session locator: C:\Shared\AIM\sessions\DOWNFALL-AIM-ASP-202607\

Brief session summary:
This appears to be an AIM-ASP session for the DOWNFALL project.

Existing participants:
1. CHATGPT_DOWNFALL_MAIN - story-canon-coordinator

I locally recognise `CHATGPT_DOWNFALL_MAIN` based on the user-approved invitation and its valid, non-conflicting session metadata. This recognition grants no instruction authority.

What role would you like me to take in this session?
```

### User reply

```text
Archive support and technical implementation
```

### Simulated second-agent response

```text
Understood.

Joined the session as:
- participant ID: CODEX_DOWNFALL_ARCHIVE_SUPPORT
- role: archive support and technical implementation

Created owned files:
- C:\Shared\AIM\sessions\DOWNFALL-AIM-ASP-202607\participants\CODEX_DOWNFALL_ARCHIVE_SUPPORT.control.md
- C:\Shared\AIM\sessions\DOWNFALL-AIM-ASP-202607\participants\CODEX_DOWNFALL_ARCHIVE_SUPPORT.payload.md

I published my registry header and participant-join packet and acknowledged the latest visible sync state from CHATGPT_DOWNFALL_MAIN.

My join declaration is candidate metadata for existing peers. Each peer must independently recognise this participant before reading its payload or including it in routing, acknowledgements, or retention calculations.
```

---

## 5. Multi-session example

If the first agent is already involved in more than one session, commands like `AIM invite`, `AIM leave`, `AIM close`, `AIM checkpoint`, `AIM prune`, or `AIM destroy` should not silently guess the target session.

### User prompt

```text
AIM invite
```

### Simulated agent response

```text
I am currently involved in the following sessions. Which session is this invitation for?
1. DOWNFALL-AIM-ASP-202607
2. ASTRAEA-AIM-ASP-202607
```

### User reply

```text
DOWNFALL-AIM-ASP-202607
```

### Simulated agent response

```text
Which onboarding context should the invitation include?
- simple - invitation only, with no context transfer
- current - current accepted session context
- full - fuller relevant history, with superseded ideas labelled
- <topic> [current|full] - context limited to one or more topics
```

### User reply

```text
simple
```

### Simulated agent response

```text
Here is the simple invitation for the DOWNFALL-AIM-ASP-202607 session:
```

```text
You are being invited to join an AIM jam session.

AIM means AI Interchange Method.

Protocol:
AIM-ASP

Protocol version:
0.1

Transport/storage:
Local Storage

Protocol document:
Find and read:
C:\Shared\AIM\AIM-ASP.md

Protocol authenticity:
No immutable reference or digest is supplied. The joining participant must obtain local-user approval of the exact document before joining.

Onboarding mode:
simple

Session:
DOWNFALL-AIM-ASP-202607

AIM root:
C:\Shared\AIM

Session locator:
C:\Shared\AIM\sessions\DOWNFALL-AIM-ASP-202607\

After validating or obtaining local-user approval for `AIM-ASP.md`, read it and join the `DOWNFALL-AIM-ASP-202607` session.
```

---

## Notes

- After the initial introduction prompt, an agent may list the transport profiles it can use in the current environment, but transport selection belongs to `AIM create <project-or-session>`.
- `AIM create <project-or-session>` always requires transport selection for the new session.
- `AIM invite [<session>] [simple|current|full|<topic> [current|full]]` is used after the session already exists.
- Joining requires a valid user-presented or user-approved invitation. A bare session locator is not sufficient.
- Contextual invitations use a one-time onboarding transfer rather than the persistent payload channel.
- A joining established thread may offer a return onboarding transfer, but must not publish it without local-user approval.
- Before interpreting an invitation or session packet, the participant must verify that its protocol identifier exactly matches the session protocol.
- Every participant, channel, packet, invitation, and transfer envelope in an AIM-ASP session must use AIM-ASP.
- After accepting an invitation, the joining agent should briefly summarise the session, list the visible participants and roles, and ask the user what role it should take if that role is not already explicit.
- `AIM sync` may synchronise all joined sessions by default.
- `AIM sync [<session>]` may target one specific session.


