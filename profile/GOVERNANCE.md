# Governance — AI-WORKFLOWS.DEV

> **Solo Governed Development**: one human, two roles, enforced separation of duties.

AI-WORKFLOWS.DEV is operated by one software engineer, Giampiero (GP). Being a solo practice is not a reason to skip process. Every change that reaches `main` goes through the same author → review → merge path a team would use, and that path is enforced by GitHub, not by willpower.

This document explains how it works, what it guarantees, and what it doesn't.

---

## 1. Roles

| Role | GitHub identity | Can | Cannot |
|---|---|---|---|
| **Lead Developer** (author) | [@aiworkflowsdev](https://github.com/aiworkflowsdev) | Write code, open PRs, respond to review, merge once `@synedrix-os` has approved | Approve own PRs, push directly to `main`, bypass rules |
| **Technical Reviewer** | [@synedrix-os](https://github.com/synedrix-os) | Review PRs, request changes, approve, merge a PR it has approved once all gates are green | Author commits, change repository rules or settings |

Both identities are operated by GP. This is disclosed openly here and on each profile. The accounts exist to separate **responsibilities**, not to imply two people.

**Invariant:** commits come only from `@aiworkflowsdev`; approvals come only from `@synedrix-os`. Anyone can verify this from the commit and review history.

**Merge rule:** a PR may be merged into `main` **only after `@synedrix-os` has approved it**, and only once every other gate in §2 and §3 is green. The approval is the permission to merge; no approval, no merge, and GitHub blocks the merge button until it exists.

- **Who may click merge:** either identity. The merge is a mechanical step performed after the decision has been made, and the decision is the approval.
- **What merging does not do:** it confers no authorship and is not an approval. Squash and rebase merges keep `@aiworkflowsdev` as the commit author, and the merge itself, with who performed it and when, is recorded in the PR timeline.
- **What it never allows:** merging a PR that `@synedrix-os` authored, or merging on the strength of any approval other than `@synedrix-os`'s. Code changes are made only as `@aiworkflowsdev`.

---

## 2. Enforced controls

These are configured as repository rulesets on `main` with **no bypass actors**, including the organization owner.

- **Pull request required**: no direct pushes to `main`.
- **1 approving review required**, from a Code Owner (`@synedrix-os`, via `CODEOWNERS`).
- **Approval must be on the most recent push**: any new commit invalidates the previous approval.
- **Required status checks must pass** before merge (see §3).
- **Conversations must be resolved** before merge.
- **Linear history**: squash or rebase merges only.
- **Force pushes and branch deletion blocked** on `main`.

Repository settings are changed only by `@aiworkflowsdev` (Owner). `@synedrix-os` has Write access and cannot alter the rules it enforces.

---

## 3. Evidence before approval

An approval means *the evidence was reviewed*, not just *the diff was looked at*. Before `@synedrix-os` approves, these must be green:

- Tests
- Lint / formatting
- Dependency and secret scanning
- Plan-governance checks (spec ↔ implementation traceability)
- Automated AI review (findings visible on the PR)

Automated findings inform the review; they don't replace it. The human decision is recorded by `@synedrix-os`.

---

## 4. Review discipline

- **Draft-first:** every PR to `main` starts as a draft. A PR opened as ready for review is converted back to draft automatically. Marking it **Ready for review** is a deliberate act, and it is what assigns `@synedrix-os` and requests their review.
- **Cooling-off period:** a PR is not approved within **4 hours** of its last push. Fresh-eyes review is
