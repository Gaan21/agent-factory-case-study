# Toward a dependable factory

**This is a design roadmap, not a report of completed capabilities.**

The goal is to accept a useful change by trying the product and examining its evidence, without
having to read every line of code. Adding more agents does not establish that this is reliable.
The factory needs a way to show what its checks catch, what they miss, and how it recovers.

## Build the evidence in stages

1. **Make the task checkable.** Give each acceptance criterion a clear check and source. Show
   which version of the result was checked, what passed and what was not checked. Record what the
   person discovers afterwards, distinguishing a defect from a new request.
2. **Make review useful and finite.** Give the reviewer short, product-specific guidance. Require
   evidence for findings and record why each was fixed or dismissed. Repeated comments should not
   keep two agents busy indefinitely; unresolved work should lead to a decision.
3. **Test the code and the running product.** Have a separate role prepare acceptance tests before
   implementation. Check that tests catch deliberately introduced defects. Repeat real user journeys
   in a disposable test environment and attach their evidence to the exact result.
4. **Test the reviewer too.** Keep confirmed examples of missed defects and known-clean changes.
   Compare reviewer configurations on the same cases, without giving away the answers. Measure
   false alarms and harmful suggestions as well as defects found.
5. **Prove recovery before unattended work.** Exercise interruptions, budgets between steps and
   maintenance that waits for work to finish. Resuming a task must preserve its work and avoid
   repeating external effects.

A specialized security review should earn its place through a measured pilot. A vote between
models is not proof that a finding is true.

## What would count as a dependable starting point?

Choose one class of changes first. Agree on the sample and acceptance thresholds before running
the evaluation. Then collect real deliveries, correction cycles and recovery exercises.

The evidence should show reproducibility, useful checks, remaining defects, human effort, model
consumption and a demonstrated way to undo a change. Report individual conditions rather than a
single quality score that could hide a serious failure behind faster delivery.

A small sample can demonstrate that the process works; it cannot establish general reliability.
Acceptance applies only to the kind of work evaluated. A person still decides what to merge and
when to deploy.

## Reference

The review improvements draw on
[How the Claude Code team does code review](https://claude.dev/blog/solving-code-review-at-anthropic/)
(October 15, 2026), especially its sections on reviewer evaluation and convergence. Its reported
results belong to that team and are not results of this factory.
