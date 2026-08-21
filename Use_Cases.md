<!--
SPDX-FileCopyrightText: 2026 Daniel Brown
SPDX-License-Identifier: MIT
-->

# Use Cases

This document collects practical examples of the kind of workflow AIM is meant to support.

## Repository planning and implementation split

One practical AIM pattern is a split planning-and-implementation workflow.

For example:

- a general ChatGPT thread handles planning, wording, review, and higher-level discussion
- a Codex or local coding thread handles repository management, file edits, and implementation

Both participants are working on the same project, but they do not naturally share memory or state. Even if one participant can edit the local repository directly, the planning participant may only have access to a transport such as Gmail Drafts.

In that setup, AIM gives each participant its own sync/control and contribution/payload channels. The planning participant can publish recommendations, summaries, or review notes. The implementation participant can sync those updates, acknowledge them, and apply the relevant changes locally with user approval.

That is a strong example of why shared storage access alone is not enough. The missing piece is not just file access. It is a coordination model that tells each participant:

- where to publish
- what it owns
- what to read first
- how to announce updates
- how to acknowledge what it has seen

## This repository as a live example

This repository itself is a good example of the kind of workflow AIM is meant to support.

One participant was a general ChatGPT planning thread working on public messaging, release framing, and documentation review. Another participant was a Codex thread working directly in the local repository with file-editing access.

Those two participants were helping with the same project, but they did not share working memory, direct file visibility, or a built-in coordination layer. AIM provided the bridge:

- the ChatGPT participant reviewed the public repository and published recommendations through its own AIM-ASP channels
- the Codex participant joined the same session, synchronised through Gmail Drafts, and acknowledged those updates through its own channels
- both participants kept separate roles while coordinating on the same repository and session

That is a practical AIM use case in one sentence: one agent helps think, review, or research, while another agent helps manage files, code, or repository state, and AIM keeps them aligned without collapsing everything into one thread.

