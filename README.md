# AI-WORKFLOWS.DEV · organization defaults

This repository holds the organization-wide governance and defaults for [AI-WORKFLOWS.DEV](https://www.ai-workflows.dev).

## Solo Governed Development

AI-WORKFLOWS.DEV is operated by one software engineer, Giampiero (GP), with a team-grade process: every change to `main` is authored, reviewed and merged through separate, permission-limited roles, and GitHub enforces that path.

| Role | GitHub identity | Does |
|---|---|---|
| Lead Developer (author) | [@aiworkflowsdev](https://github.com/aiworkflowsdev) | Writes code and opens pull requests |
| Technical Reviewer | [@synedrix-os](https://github.com/synedrix-os) | Reviews and approves; never authors commits |

Both identities are operated by the same person, and this is disclosed openly. The separation is of **responsibilities**, not of people. Its honest limit is stated in the governance document: it protects against shortcuts and lapses, not against collusion.

## Contents

| File | Purpose |
|---|---|
| [GOVERNANCE.md](GOVERNANCE.md) | The full process: roles, enforced controls, evidence before approval, review discipline, guarantees and limits |
| [PULL_REQUEST_TEMPLATE.md](PULL_REQUEST_TEMPLATE.md) | The default pull request description the author fills in: what and why, plan or spec, how it was checked, risk |
| [REVIEW_TEMPLATE.md](REVIEW_TEMPLATE.md) | The structured review record the Technical Reviewer posts on every pull request |

## How to verify it

The process leaves a public trail. In any repository that follows it:

- commits are authored by `@aiworkflowsdev`;
- approvals come only from `@synedrix-os`;
- each approval carries a review record in the format of the template above;
- direct pushes to `main` are blocked, and pull requests start as drafts.

## Questions or audit requests

Open an issue in this repository.
