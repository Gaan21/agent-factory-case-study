# Case study maintenance instructions

## Purpose

This public repository explains how a personal agent factory works and evolves,
in plain language. It is a visual, evolving case study, not an operations manual
or a copy of the private project.

## When updating it

- Write all repository content in **English**, including diagrams and agent instructions.
- Read `README.md` first and keep the introduction short and understandable.
- Explain each component in plain language before using its technical name.
- After a relevant, verified advance, update the explanation that has changed.
  Add a diagram, example, or result only when it helps readers understand it.
- Distinguish design, work in progress, and verified behavior. Do not present a
  proposal as implemented or extrapolate a test into a general guarantee.
- Explain the problem, the change, and its evidence. Include concrete limitations
  or lessons when relevant.
- Prefer Markdown and Mermaid, which GitHub renders directly. Avoid creating a
  website or adding build tools without an agreed need.
- Do not create empty sections for future work or a session-by-session diary.
- If nothing relevant to the reader has changed, do not add content routinely.

## Publishable material

Use the design material prepared for publication in the private project as the
writing source. Do not extract material from its operational records, status
documents, runbooks, transcripts, or infrastructure documentation.

Use fictional names and data in examples. Do not include private repository names,
agent accounts, hosts, network addresses, actual filesystem paths, credentials,
authenticated configurations, or links to private documentation. Screenshots and
results must be prepared specifically for publication.

Before delivering an update, review the diff, links, and consistency between
diagrams and text. The agent prepares the content; the project owner publishes it.
