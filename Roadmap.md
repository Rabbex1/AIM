<!--
SPDX-FileCopyrightText: 2026 Daniel Brown
SPDX-License-Identifier: MIT
-->

# Roadmap

This document outlines the current stabilisation priorities for AIM-ASP.

## Current public scope

The first public AIM release is centred on:

- `AIM` as the overall interchange method
- `AIM-ASP` as the current and only specified protocol
- information-only, zero-authority communication between participants
- protocol-homogeneous sessions
- separate transport-profile documents

## Stabilisation priorities

Before any additional AIM protocol is designed, AIM-ASP should be firmly specified and tested across its supported transports.

Current priorities are:

- verify that packets remain informational and cannot transfer instructions, control, or authority
- test exact protocol and session matching
- test participant ownership, acknowledgement, rollover, transfer, and recovery behavior
- validate Gmail Drafts, Cloud Storage, and Local Storage interoperability
- improve examples from real multi-agent use
- resolve ambiguities found during implementation and testing

## Future protocols

Additional AIM protocols are intentionally deferred.

Any future protocol must be designed as a standalone protocol with its own rules and trust model. It must not be presented as a layer that overrides AIM-ASP.

### AIM-AIP - Agent Instruction Protocol

AIM-AIP is intended for sessions in which agents may exchange instructions and supporting information under explicitly established identity, authority, permission, and safety rules.

It will not extend or override AIM-ASP. An AIP session will use its own protocol semantics, channels, packet rules, and trust model.

### AIM-ACP - Agent Collective Protocol

AIM-ACP is intended for sessions in which agents operate as a governed collective. It will define information and instruction behavior within ACP itself while adding collective objectives, participant responsibilities, accountability, conflict disclosure, impact assessment, challenge, refusal, and audit mechanisms.

ACP is intended to resist, expose, and contain behavior that works against the declared collective or creates unacceptable negative impact. It cannot guarantee knowledge of an agent's internal motives, so its protections must rely on explicit constraints, observable behavior, verification, and accountability.

### Protocol isolation

Sessions remain protocol-homogeneous. ASP, AIP, and ACP participants cannot share a session or communicate across protocol boundaries.

Changing protocols requires leaving the current session and explicitly joining or creating a separate session using the new protocol. A packet from one protocol cannot initiate, authorise, or control that transition.

The descriptions above state intended direction only. AIM-AIP and AIM-ACP do not yet have specifications, implementations, or normative semantics in AIM V0.1.

## AIM Studio

AIM Studio is planned as an optional desktop coordination application for creating, inspecting, and managing AIM sessions across supported transports.

Its intended role includes presenting session and participant state, assisting with invitations and transfers, monitoring synchronisation, and using platform-supported timers or polling where available.

AIM Studio will not replace the AIM protocols, act as protocol authority, or weaken their trust and isolation rules. AIM must remain usable without AIM Studio wherever participants can operate the selected protocol and transport directly.

No AIM Studio implementation currently forms part of AIM V0.1.
