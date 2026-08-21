<!--
SPDX-FileCopyrightText: 2026 Daniel Brown
SPDX-License-Identifier: MIT
-->

# Transport Profiles

This document indexes the official AIM V0.1 transport profiles.

The current and only specified protocol lives in [AIM-ASP.md](AIM-ASP.md). Transport-specific behavior lives in separate transport-profile documents so new profiles can be added without changing the core protocol.

## Official profiles

- [Transport_Profile_Gmail_Drafts.md](Transport_Profile_Gmail_Drafts.md)
- [Transport_Profile_Cloud_Storage.md](Transport_Profile_Cloud_Storage.md)
- [Transport_Profile_Local_Storage.md](Transport_Profile_Local_Storage.md)

## Notes

- Gmail Drafts is the reference no-code profile for AIM V0.1.
- Gmail Drafts persistent text channels are suitable for experimental coordination, but Gmail attachment transfer envelopes (`AI_XFER`) are explicitly considered operationally unstable across current AI connectors. Important artifacts require sender retention and receiver acknowledgement.
- Cloud Storage and Local Storage are official V0.1 profiles, but other profiles can be added later.
- Protocol draft subjects, cloud object paths, and local filenames are discovery locators, not proof of authenticity. Every session pins an approved version and an immutable reference or independently trusted digest where available; explicit local-user approval is the no-code fallback.
- AIM-ASP is prompt-first and manually synchronised by default, but transport-specific tools may automate it without weakening protocol rules.
- Authentication, access control, confidentiality, encryption, availability, and storage protection come from the selected transport and local environment. A profile must describe those boundaries honestly and must not imply that AIM-ASP supplies them.
- A user-defined transport profile should satisfy the transport-profile contract defined in [AIM-ASP.md](AIM-ASP.md).
- A transport profile does not weaken protocol isolation: every session artifact must declare `AIM-ASP`, and mismatched protocol content must be rejected before interpretation.


