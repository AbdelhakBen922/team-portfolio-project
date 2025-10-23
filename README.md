# team-portfolio-project

This repository contains our team portfolio project for the Software Engineering module.

## Contributors (Definitive List)
- Abdelhak Benbouziane (Team Leader) — [@AbdelhakBen922](https://github.com/AbdelhakBen922)
- Zakaria Chetouane — [@2EDX7](https://github.com/2EDX7)
- DhiaaEddine Guerfi — [@Dhia0Eddine](https://github.com/Dhia0Eddine)
- Ala Slimani — [@AlaSlimani99](https://github.com/AlaSlimani99)

## Deployed Website
- Visit the site on GitHub Pages: [team-portfolio-project website](https://abdelhakben922.github.io/team-portfolio-project/)

## Team Retrospective Analysis 

### Most significant technical challenge
Overall, the development was straightforward with few blocking issues. The most notable challenge was branch base management rather than code complexity. At times, feature branches were created from an outdated or incorrect base (neither `main` nor `develop`), which led to divergent histories. This caused some pull requests to show “no changes” because their commits already existed on the target branch under different SHAs. In one instance, a merge moved the `develop` branch in a way that made previously merged work appear to be missing. The underlying issue was inconsistent branching from the correct upstream state and, at least once, merging against an unintended history.

### Specific merge conflict and how we resolved it
When we noticed the “PR has no diff” symptom and the unexpected `develop` history, we took a clean, controlled approach:
1) Recreated `develop` from the correct upstream state to ensure a reliable base.  
2) Rebased the affected feature branches onto the new `develop` (`git fetch`, `git rebase origin/develop`) so conflicts surfaced locally.  
3) Resolved conflicts file-by-file, keeping the intended content and removing duplicates, then ran formatters to minimize cosmetic diffs.  
4) Force-pushed the feature branches (only our personal branches) and re-opened PRs to validate that the diffs reflected the intended changes.  
5) Re-merged into `develop`, confirming that prior work remained intact and the history was consistent.

### Effectiveness of PRs and peer reviews
Even with minimal technical hurdles, the PR and peer review workflow improved quality and confidence. Small, focused PRs made reviews fast and precise, helping us catch minor issues (inconsistent spacing, missing alt text, and responsive layout tweaks) before they reached `develop`/`main`. Reviews also aligned the team on conventions and shared context for future changes. With branch protection and approvals, merges were more deliberate, and the audit trail (discussion + commits) made it easy to diagnose history issues quickly. Overall, PRs and reviews enhanced code consistency, reduced regressions, and ensured the final artifact met our standards.
