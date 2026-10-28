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

This is a tested local candidate, not an installed gate. A pass only covers resource integrity.
It does not prove coverage of every screen, separate document, language quality, or behavior in
the factory's runtime. The combined translation gate is still work in progress.
