# ci-postmortem-drill

A small, self-contained sandbox for **blameless-postmortem training**.

## What this is

This repository is a safe, re-runnable environment for practicing incident
triage during our team's blameless-postmortem workshop. Nothing here touches
production: it exists purely so participants can walk through the mechanics of
an incident review — collecting CI evidence, building a timeline, and writing
findings — against a deliberately simple, fully controllable codebase.

## The CI definition

The CI that we triage during the drill lives at:

    .github/workflows/demo-ci.yml

That workflow is **manually triggered** (`workflow_dispatch`). It runs a single
trivial Linux job with two steps that echo `starting drill` and then
`drill complete`, and it exits successfully. Because it is harmless and
fast, it can be re-triggered at any point during the session to generate fresh
runs for the group to examine.

## How to use it in a session

1. Open the **Actions** tab and trigger `demo-ci` on the default branch.
2. Watch the run progress, then pull its logs.
3. Triage the evidence using the open drill issues:
   - `Drill: collect CI evidence`
   - `Drill: write timeline`
4. Discuss findings — focusing on systems and process, not individuals.

## Ground rules

- **Blameless by design.** The goal is learning, not fault-finding.
- **Leave things open and unmerged.** The sandbox should stay clean and
  re-runnable so every cohort gets the same starting state.
