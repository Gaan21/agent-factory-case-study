# Keep the rules small, not hidden

Moving instructions out of an agent's starting file can make that file shorter. It can also make
the instructions disappear from the work.

The change here separates three things:

| Always present | Read before the relevant work | Maintained elsewhere |
|---|---|---|
| Product limits and delivery checks | Local test, tool and release procedures | Shared guides and upstream technical references |
| A short guide index | Product architecture and design contracts | Framework knowledge maintained by its authors |

The starting file says **“before doing this, read that section.”** It does not just link to a large
manual. Important limits stay in the starting file, even when the full procedure moves out.

The same repository instructions serve direct work with a person and factory tasks. Each project
selects the guides it needs. A local connection supplies their index to Claude Code and OpenCode
through ignored files, without rewriting the tracked project instructions. The agent reads a topic
when the task needs it, rather than loading every topic at the start.

We also removed local skills that only wrapped external references to repeat “our rules come
first.” Before removing them, we kept the actual product decisions: visual identity, languages,
backend ownership, adopted architecture and cache policy. A local release procedure is not a
framework tutorial, so it stays local.

## What was checked

- Direct-work guide connections across an app, a public website and an operational panel.
- Connect, check and disconnect trials in temporary copies before connecting the working projects.
- Missing-guide warnings with connected and disconnected fixtures; native OpenCode V2 plugin activation.
- One effective guide-index registration in OpenCode. The owner also checked the imports in Claude Code.
- The panel's thirteen retained external references appeared in OpenCode's native catalog from the
  folder shared with Claude, without the local flags that previously hid them.

These checks establish connection and visibility, not better code or reliable compliance. A reading
instruction is not a security boundary. Reference skills still need maintenance.

## Refresh before loading, not just before answering

A startup hook looked like the obvious place to refresh guides. A local fixture showed that Claude
Code had already read the imported index before that hook finished. Its first outgoing request
still contained the old index, even though the file now held the new one. Preparing the file before
opening the client delivered the new text instead. No real model provider was called for that check.

The chosen direct-work workflow is one explicit refresh command, followed by the usual client
command. It was checked across the three working projects: selected sources fetched, connection
verified, new reference saved, and no tracked files changed by the refresh. Download failure may
use the last intact copy with a stale-copy warning; an altered prepared copy is not that fallback.

Updating the tool itself also exposed a check that demanded the exact executable that had prepared
the guides. That confused provenance with compatibility. The current tool now checks the retained
selection, supported format, content and connection instead. Recording how a selection was prepared
does not mean keeping that executable forever. Shared evidence for the two roles of one task is
still compared separately.

This is direct-work preparation, not an automatic startup hook or a code-quality result. Resolving
the latest guides automatically for each new factory task remains pending.

**Useful question:** when moving an instruction, what tells the agent to find it before it matters?
