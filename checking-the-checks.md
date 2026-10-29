# Checking the checks

**A green translation check does not mean every user-facing message is translated.** It only
means that the check accepted what it looked at.

Before adding translation checks to the factory, we measured existing tools on small, separate
samples. Each tool got a clean sample first. Then we changed one thing at a time and kept its
output. We used the real checker scripts and isolated lint rules, not full application builds.

Two results changed the plan:

- A check could reject a missing key in an English file, yet accept the whole English file being
  absent. It compared the files it found, not the languages the product promised.
- A parameter check based on text patterns accepted a broken plural message and rejected a valid
  one. It read words inside the plural branches as parameter names. The real message parser
  accepted the valid sample and rejected the broken one.

Text detection also had gaps. A web rule found text between tags but missed the same text inside
an expression. Another rule missed messages with punctuation or interpolation, but flagged a
technical log and a brand name. These were controlled examples, not a count of bugs in the apps.

## What this changes

The factory needs a common rule, not one parser for every product:

1. Declare the languages the product must provide.
2. Check resources with a parser that understands their actual format.
3. Detect direct text in known user-facing places.
4. Review the affected paths that automation cannot establish, including documents, metadata and
   messages coming from other parts of the system.

**Detection, warnings and blocking are different things.** A rule that reports a warning in an
isolated test does not prove that the full project command will reject a change.

## The first piece: resource files only

A local checker now uses each project's declared languages and message format. It checks missing
files, empty messages, structure and parameters. It uses real parsers for plural messages rather
than guessing their syntax from text patterns.

Lists need an explicit contract: messages translated by index are not the same as data returned
without interpretation. Missing tools or an unsupported structure produce an incomplete result,
not a pass. Tests use clean and planted samples, plus copies of real resources without changing
the originals.

The first tests were local. The installed trial is described below; a pass still only covers
resource integrity. It does not prove coverage of every screen, separate document, or language
quality. The combined translation gate is still work in progress.

## The second piece: text that skipped the translation system

The products already read their texts from language files. The remaining risk is a change that
writes a button label such as "Save" straight into the code instead. Catalogs that match perfectly
cannot see that.

The detector has two parts:

- **One common rule** for every technology. It blocks text with letters in a place a person sees:
  screen content, attributes and parameters whose last word is `label`, `title`, `hint`, `message`
  or similar, metadata, notices and dialogs, system prompts, and a technical error shown as is.
  Logs, internal errors, routes, URLs, symbols and declared brand names do not count.
- **One reader per language.** It walks the code with that language's real parser and only lists
  each text with where it appears. It decides nothing. A new framework needs a reader, not a new rule.

There are no exclusions by length, punctuation, folder or key: "No" or "Save." on a button blocks.
What the analysis cannot classify, such as a sentence in an unrecognized property or an error shown
only by its variable name, becomes a doubt for the reviewer, who follows the path. A legitimate case
is justified next to the text, with its reason, and the reviewer decides.

A simple writing rule keeps this practical: logs and internal errors use one technical language and
never reach the screen; an error that reaches a person carries a code that the screen translates.
The detector watches where text is shown, not every error that is raised.

It scans all declared code, not only the change. The first run on copies of real products mostly
found the detector's own false positives, such as a technical word that happened to end like a
visible one. They were fixed with general rules and a test case each. An independent review then
found chained errors and notice calls that slipped through. The final run reports a few real cases,
such as a system notification channel name fixed in one language.

Those first tests used seeded cases in three syntaxes and read-only copies. Text that arrives
through variables or from a server still needs path review.

## Installed and tested is not enabled

Both checks now have a shared connection to the task workflow, separate from each technology's
code tests. They read the product in a read-only box with no network, using pinned tools and
project descriptions kept outside the product. They do not load its scripts, plugins, or settings.

The installation has been exercised on Linux with clean samples and planted mistakes across the
three project profiles. Tests check the expected results, unchanged inputs, read-only mounts,
the absence of personal folders, and a separate network space. This is not a general security
audit or coverage of every output of an application.

The first launch refused to start because the environment required the isolation options to be
expressed differently. The launcher was corrected without removing isolation, then tested in the
actual environment. Passing the local tests had not established that compatibility.

**The checks remain disabled.** Before they become a requirement for tasks, the current products
still need to be checked and the route from a detector's doubt to the reviewer's evidence needs
to be completed. For now, doubts and written justifications block; they are not automatic passes.

Installed, exercised on samples, and enabled to accept a deliverable are three different results.
A test of the checker is not a guarantee about the product.
