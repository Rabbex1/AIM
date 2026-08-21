<!--
SPDX-FileCopyrightText: 2026 Daniel Brown
SPDX-License-Identifier: MIT
-->

# Governance

## Purpose

This document explains how the public AIM project is governed.

It is separate from the legal license. The license defines what reuse is permitted. This document defines which specification is canonical, how versions are published, how compatibility should be described, and how extensions and forks should present themselves.

## Canonical specification

The canonical public specification for AIM is the version published in the official **Rabbex1/AIM** repository.

At the time of writing, the core specification is defined by:

- `AIM-ASP.md`
- `Transport_Profiles.md`
- the official `Transport_Profile_*.md` documents

Supporting documents such as `README.md`, `AGENTS.md`, `Technical_Overview.md`, `Demo_Workflow.md`, and the use-case files are explanatory material. They help humans and agents use AIM, but they do not override the canonical specification.

If two documents appear to conflict, the canonical specification documents take priority over explanatory material.

Repository branch names, mutable files, and `CURRENT` aliases are discovery conveniences, not immutable release identifiers. A session that requires verifiable protocol authenticity should pin an official repository commit or release object and, where practical, an independently obtained SHA-256 digest.

If immutable verification is unavailable, AIM-ASP permits explicit local-user approval of the exact protocol document. That fallback establishes local acceptance only; it must not be described as cryptographic verification or steward authentication.

## Stewardship

The public AIM project is currently stewarded by **Rabbex1**.

For attribution and copyright purposes, **Rabbex1** is the GitHub identity of **Daniel Brown**.

The project steward is responsible for:

- publishing canonical specification updates
- defining official versions
- accepting, rejecting, or revising proposed changes
- declaring official transport profiles
- clarifying ambiguities in the public specification

## Versioning

AIM versions are published by the project steward.

Version numbers should be interpreted as specification versions, not merely repository snapshots.

In general:

- patch versions clarify wording, fix examples, and correct errors without changing intended protocol behavior
- minor versions add or refine protocol behavior while preserving broad compatibility where practical
- major versions introduce deliberate breaking changes to the canonical specification

Before AIM reaches long-term stability, pre-1.0 versions may still contain meaningful protocol changes.

## Compatibility

Compatibility should be described plainly.

An implementation, profile, or extension should not describe itself as compatible with AIM unless it can follow the canonical rules that matter for safe coordination, including:

- information-only communication with no transferred instructions, control, or authority
- protocol-homogeneous sessions and exact protocol matching
- participant-owned channels or files
- no modification of other participants' owned state
- structured sync and payload behavior
- session and participant identity rules
- safety and authority boundaries

When compatibility is partial, say so explicitly.

Recommended wording:

- `Compatible with AIM vX.Y`
- `Partially compatible with AIM vX.Y`
- `Inspired by AIM`
- `AIM extension for <transport-or-platform>`

## Extensions and transport profiles

AIM is designed to be extensible.

New transport profiles, helper tools, automation layers, and implementation guides may be created without changing the core protocol, provided they do not misrepresent themselves as the canonical specification.

Good extensions should:

- identify the AIM version they target
- describe what they add, restrict, or automate
- preserve the core safety and ownership rules
- preserve AIM-ASP's information-only and protocol-isolation boundaries
- make clear whether they are official or third-party

Third-party extensions should not silently redefine the core protocol.

## Forks and modified versions

Forks are permitted by the project license, but they should be described honestly.

If you publish a modified version that changes protocol behavior, naming, semantics, ownership rules, safety boundaries, transport assumptions, or compatibility expectations, you should clearly state that it is a modified or forked version.

Recommended wording:

- `Fork of AIM`
- `Modified from AIM`
- `Based on AIM`

Incompatible forks should not present themselves as the canonical AIM specification.

## Naming

`AIM` refers to the public protocol as defined by the canonical specification in the official repository.

Extensions, forks, and experimental variants should avoid creating confusion about whether they are the canonical specification.

In practice, that means:

- use the AIM name clearly when referring to the canonical protocol
- label unofficial variants as extensions, forks, adaptations, or experiments
- do not imply steward approval where none exists

If a separate trademark or naming policy is published later, that document will add to this section.

## Proposed changes

Public feedback, discussion, examples, and proposed improvements are welcome.

Suggested changes may be submitted through normal repository collaboration mechanisms such as issues, discussions, or pull requests where available.

Submitting a suggestion does not by itself make the change part of the canonical specification.

A change becomes canonical only when it is accepted and published by the project steward in the official repository.

## Stability policy

AIM aims to remain understandable, inspectable, and stable enough for humans and agents to use across different tools and transports.

Changes should prefer:

- clarity over cleverness
- compatibility over churn
- explicit extensions over silent behavior changes
- canonical updates over fragmented reinterpretation

## Relationship to the license

This file is a governance and stewardship document. It is not the legal license.

The binding legal reuse terms for the repository are defined in [LICENSE](LICENSE).


