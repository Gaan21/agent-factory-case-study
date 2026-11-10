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

This is direct-work preparation, not an automatic startup hook or a code-quality result.

## Fresh between tasks, stable within a task

An implementer and its reviewer need the same rules, even if the guides change while the work is
in progress. That does not require freezing the whole factory on an old version.

The new task-preparation path fetches the selected guide sources, records their exact commits and
retains their files. The next task resolves the branch again; corrections and review reuse the
current task's retained selection without downloading again. If the initial download fails, the
task stops rather than labelling an old mirror current.

Local tests with the real guide tool checked that a guide update reaches the next task without
changing the previous one, and that the previous task's reviewer still receives its original
selection. The actual app, website and panel selections were also prepared locally: translation
and design topics were readable, with matching selections for both roles.

## Required context is not something the project manager must remember

A product-wide design contract can live in a different repository from the code being changed.
Each factory configures its own repository list. When it requires the complete product, a program
adds omitted repositories for consultation **before approval**; the approved task shows that list.
It does not silently add sources to an already approved task or lend another factory's access.

A check requires the design contract to be present, readable, nonempty and not reached through
links. Both roles are told where to find the original, not given another copy of its policy.
Local trials with the real repositories delivered the complete product when starting from each
of its three code surfaces. Missing-context cases were tested separately and stopped before an
agent session could begin.

The preparation path and required-context checks are now **installed and tested on the execution
machine**. The tests ran against the installed modules, as the normal unprivileged coordinator,
in an isolated process with no outside network and no access to the real task record. The existing
guide tool prepared the three real selections without an update. Translation and design topics
were readable, and the reviewer view reused the retained selection.

This was not a new real agent task. Product bases were synthetic; transport and models were
simulated. No product code ran, and automatic task admission stayed closed. These checks do not
prove native runtime loading, model compliance or better code. Writing across repositories,
including updating product knowledge within the same task, remains a separate increment. The
shared translation policy comes from the guides; supplying it does not activate new product checks.

**Useful question:** when moving an instruction, what tells the agent to find it before it matters?
