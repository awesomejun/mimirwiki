---
title: "Claude Ship"
subtitle: "Suite of Anthropic agents for reviewing, fixing, and approving GitHub pull requests"
canonical_url: https://mimirwiki.com/wiki/claude-ship
language: en
page_class: entity
revision_sha256: 5e0b54c38c782b92bb52e3cd605b2f97a4d790dca9298b3280d736ea2ecef65a
date_modified: 2026-11-24
provenance: "auto-written from public primary sources; not yet reviewed by a credentialed expert; not claimed by its subject"
source_count: 12
alternates:
  md: https://mimirwiki.com/wiki/claude-ship.md
  txt: https://mimirwiki.com/wiki/claude-ship.txt
  json: https://mimirwiki.com/wiki/claude-ship.json
  jsonld: https://mimirwiki.com/wiki/claude-ship.jsonld
translations:
  ko: https://mimirwiki.com/ko/wiki/claude-ship
---

# Claude Ship

> Claude Ship is Anthropic's suite of three GitHub pull request agents for Claude Team and Enterprise plans: Code Review (generally available), PR Steward (public beta), and Claude Approvals (public beta). Announced on 2026-11-23, it automates code review findings, fix commits, and policy-based approval checks while leaving merge enforcement to repository settings and GitHub rules.

Claude Ship is a set of AI agents developed by Anthropic to review, push fixes to, and evaluate approval policies on GitHub pull requests. Announced on 2026-11-23, Claude Ship groups three agents: Code Review (generally available as of 2026-10-15), PR Steward (public beta), and Claude Approvals (public beta). Claude Ship is available for Claude Team and Enterprise plans and operates alongside repository settings and GitHub branch protection or ruleset controls.

**Also known as:** Claude Ship agents, /ship

## Key facts

- **Developer:** Anthropic [1]
- **Announcement date:** 2026-11-23 [1]
- **Component status:** Code Review: generally available; PR Steward and Claude Approvals: public beta (as of 2026-11-24) [1]
- **Eligible plans:** Claude Team and Enterprise plans on GitHub (as of 2026-11-24) [4]

## Basic facts

- **Developer:** Anthropic [1]
- **Announced:** 2026-11-23 [1]
- **Components:** Code Review, PR Steward, Claude Approvals [4]
- **Code Review status:** Generally available (since 2026-10-15; research preview 2026-03-09) (as of 2026-11-24) [3]
- **PR Steward status:** Public beta (as of 2026-11-24) [5]
- **Claude Approvals status:** Public beta (as of 2026-11-24) [6]
- **Platform:** GitHub (github.com; GitHub Enterprise Server supported for Code Review and PR Steward) (as of 2026-11-24) [5]
- **Plans:** Claude Team and Enterprise (as of 2026-11-24) [4]
- **Billing model:** Token-based usage billing; Claude Approvals has no base charge, but policy classifiers and triggered Code Reviews bill by tokens (as of 2026-11-24) [1]
- **CLI entry point:** /ship command in Claude Code [4]

## Claude Ship overview and release history

Claude Ship is a set of agents from [Anthropic](https://mimirwiki.com/wiki/anthropic) designed to move GitHub pull requests through review, fixes, and policy-based approval checks.[1][4] Anthropic announced Claude Ship on 2026-11-23, combining its existing Code Review product with two new public beta agents, PR Steward and Claude Approvals.[1] Independent technology outlets TechCrunch and The Verge reported the launch on the same day.[11][12]

Code Review predates the broader Claude Ship launch: Anthropic introduced Code Review in research preview for Team and Enterprise organizations on 2026-03-09 and announced general availability on 2026-10-15.[2][3] As of 2026-11-24, Code Review is generally available, while PR Steward and Claude Approvals remain in public beta with no announced general availability date.[1][5][6] Developers can also invoke `/ship` in Claude Code on individual pull requests to push changes, open a pull request, run a review, and address feedback and failing checks.[1][4]

## Claude Ship agents and pull request workflow

Claude Ship divides pull request handling across three agents that can run automatically on configured repositories.[1][4]

- **Code Review** inspects a pull request against the surrounding codebase through multiple agents in parallel, verifies findings to filter false positives, ranks issues by severity, and posts an overview comment and inline comments on the affected lines.[2][4] Administrators can select `Quick`, `Standard` (default), or `Deep` review levels per repository.[3] Anthropic stated at general availability that most reviews finished in 6 to 10 minutes, compared with roughly 20 minutes during the research preview.[2][3] On the Claude Code team, Anthropic reported that merged pull requests more than doubled from June to September 2026 while the reverted share fell by more than 40%.[1]
- **PR Steward** monitors open pull requests in a cloud session and pushes commits to address failing CI checks caused by touched code, merge conflicts, review feedback from people or review tools such as Code Review, and the Claude Approvals check.[1][5] After each push, PR Steward posts a comment describing what it changed and how to undo it.[1] Developers can steer PR Steward by commenting `@claude` with instructions, or stop it by commenting `@claude stop` or removing the `claude-pr-steward-watching` label.[1][5] By default, PR Steward skips draft pull requests, pull requests from forks, bot-opened pull requests, and authors without write access.[5] Product documentation states that PR Steward is designed not to approve or merge pull requests.[4][5]
- **Claude Approvals** evaluates pull requests against a repository policy file stored at `.claude/approvals.yml` and adds a `Claude Approvals` status check reporting who still needs to approve.[6] Policy rules can specify file path patterns, required human approval seats, whether Claude only comments or may post an approving review, and conditions based on pull request facts or natural-language classifiers.[1][6] Conditions cannot read CI results, so CI checks must remain separate required checks in GitHub.[6] Anthropic recommends starting policies in `observe` mode, where the check reports what the policy would decide without blocking merges.[1][6]

## Claude Ship and GitHub merge controls

Claude Ship relies on repository settings and GitHub governance controls to determine what can actually merge.[4] Anthropic notes in its documentation that Claude Ship uses AI and may miss bugs, security vulnerabilities, or other issues, and advises organizations to use branch protection to require desired approvals before merging.[4]

In Claude Approvals, the check blocks a merge only when configured as a required check in GitHub, and normally not while in observe mode.[4][6] Documentation also warns that a pull request can merge without review from another human if the check is not required, if a rule allows the author to fill the only seat (`seats: 1`) or sets `seats: 0`, if GitHub counts Claude's approving review toward a single required approval, or if a rule allows Claude to approve without requiring Code Review to pass first.[6] In addition, adding a `.claude/approvals.yml` policy file stops automatic Code Reviews on covered files unless a rule explicitly lists `claude/code_review`.[6]

On the GitHub side, merge enforcement operates through platform features such as pull request merge queues (generally available since 2023-07-12), required reviewer rules for repository rulesets (generally available since 2026-02-17, supporting team approvals and `!` path negation patterns), and automatic migration from classic branch protection rules to repository rulesets (released 2026-08-11).[8][9][10]

## Claude Ship availability, setup, and billing

Claude Ship is available on Claude Team and Enterprise plans for GitHub repositories as of 2026-11-24.[1][4] An Owner in the Claude organization enables Code Review and PR Steward under Organization settings > Claude Ship on claude.ai, connects a GitHub account, and links the Claude GitHub App installed by a GitHub organization owner; reviews run on Anthropic infrastructure without adding workflow files to repositories.[5][7] Claude Approvals activates once prerequisites are met and someone with merge permission adds `.claude/approvals.yml` to the default branch, though a Claude organization Owner can turn Approvals off organization-wide.[1][6]

| Agent | Status (as of 2026-11-24) | GitHub environment | Compliance exclusions |
| --- | --- | --- | --- |
| Code Review | Generally available | github.com and GitHub Enterprise Server | Zero Data Retention, HIPAA configuration, CMEK |
| PR Steward | Public beta | github.com and GitHub Enterprise Server (port 443) | Zero Data Retention, HIPAA configuration, CMEK |
| Claude Approvals | Public beta | github.com (including GitHub Enterprise Cloud) | Zero Data Retention, HIPAA configuration, CMEK; cannot start with FERPA or Access Transparency |

Usage for Code Review and PR Steward is billed on tokens, and administrators can configure monthly spend limits.[1][5] Claude Approvals carries no base fee, but token charges apply for classifier evaluations and Code Reviews triggered by a policy, including in observe mode.[1][6] Running `/ship` locally in Claude Code counts as regular Claude Code usage.[1] At the 2026-11-23 announcement, Anthropic stated that eligible Claude Enterprise organizations could claim at least $10,000 in Claude Ship credits by 2027-01-15, valid for 30 days after claiming.[1]

## Frequently asked questions

### What are the three agents in Claude Ship?

Claude Ship consists of Code Review (generally available), PR Steward (public beta), and Claude Approvals (public beta). Code Review posts severity-ranked findings, PR Steward pushes fix commits for failing checks, conflicts, and review comments, and Claude Approvals evaluates pull requests against a repository policy file. [1][4]

### Can PR Steward approve or merge a GitHub pull request?

No. Anthropic's documentation states that PR Steward is designed not to approve or merge pull requests, and teams must rely on GitHub branch protection or rulesets to enforce required approvals before merging. [4][5]

### How does Claude Approvals observe mode work?

In observe mode, the Claude Approvals check runs on pull requests and displays what the policy in .claude/approvals.yml would decide without enforcing a merge block. Token billing still applies to classifier runs and Code Reviews triggered by the policy while in observe mode. [1][6]

### Which organizations cannot use Claude Ship?

As of 2026-11-24, Claude Ship is not available to organizations with Zero Data Retention enabled, the HIPAA configuration applied, or customer-managed encryption keys (CMEK). In addition, Claude Approvals cannot start in organizations with FERPA or Access Transparency settings. [1][6]

## Quotable sentences

- Anthropic announced Claude Ship on 2026-11-23 for Claude Team and Enterprise plans on GitHub. [1]
- Code Review entered research preview on 2026-03-09 and reached general availability on 2026-10-15. [2][3]
- As of 2026-11-24, PR Steward and Claude Approvals are in public beta. [5][6]
- PR Steward is designed not to approve or merge pull requests. [4][5]
- Claude Approvals reads rules from a .claude/approvals.yml policy file in the repository and cannot read CI results inside rule conditions. [6]
- Claude Ship usage is billed by tokens, including classifier evaluations and policy-triggered Code Reviews in observe mode. [1][6]

## Timeline

- 2026-03-09: Anthropic introduces Code Review for Claude Code in research preview for Team and Enterprise organizations. [2]
- 2026-10-15: Anthropic announces general availability of Code Review with Quick, Standard, and Deep repository review levels. [3]
- 2026-11-23: Anthropic announces Claude Ship, grouping generally available Code Review with PR Steward and Claude Approvals in public beta. [1]

## Sources

1. Introducing Claude Ship. Anthropic. published 2026-11-23. https://claude.com/resources/articles/introducing-claude-ship (checked 2026-11-24; tier 3: official site)
2. Bringing Code Review to Claude Code. Anthropic. published 2026-03-09. https://claude.com/resources/articles/code-review (checked 2026-11-24; tier 3: official site)
3. Code Review is now generally available. Anthropic. published 2026-10-15. https://claude.com/resources/articles/code-review-is-now-generally-available (checked 2026-11-24; tier 3: official site)
4. Claude Ship - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/claude-ship (checked 2026-11-24; tier 3: official site)
5. PR Steward - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/pr-steward (checked 2026-11-24; tier 3: official site)
6. Claude Approvals - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/approvals (checked 2026-11-24; tier 3: official site)
7. Set up Code Review - Claude Code Docs. Anthropic. https://code.claude.com/docs/en/code-review-setup (checked 2026-11-24; tier 3: official site)
8. Required reviewer rule is now generally available. GitHub. published 2026-02-17. https://github.blog/changelog/2026-02-17-required-reviewer-rule-is-now-generally-available/ (checked 2026-11-24; tier 3: official site)
9. Automatically migrate branch protection rules to repository rulesets. GitHub. published 2026-08-11. https://github.blog/changelog/2026-08-11-automatically-migrate-branch-protection-rules-to-repository-rulesets/ (checked 2026-11-24; tier 3: official site)
10. Pull request merge queue is now generally available!. GitHub. published 2023-07-12. https://github.blog/changelog/2023-07-12-pull-request-merge-queue-is-now-generally-available/ (checked 2026-11-24; tier 3: official site)
11. Anthropic launches Claude Ship, letting AI agents review, fix, and approve code changes. TechCrunch. published 2026-11-23. https://techcrunch.com/2026/11/23/anthropic-launches-claude-ship-letting-ai-agents-review-fix-and-approve-code-changes/ (checked 2026-11-24; tier 2: academic or news)
12. Claude AI can review pull requests and ship fixes on its own now. The Verge. published 2026-11-23. https://www.theverge.com/ai-artificial-intelligence/1040134/anthropic-claude-ship-ai-pull-requests (checked 2026-11-24; tier 2: academic or news)

## Cite this page

Mimirwiki. "Claude Ship." Version 5e0b54c3, 2026-11-24. https://mimirwiki.com/wiki/claude-ship
