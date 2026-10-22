# GitHub Activity Audit — HeziLiu
Audit date: 2026-10-22 (UTC). Scope: profile HeziLiu (verified via authenticated identity, login `HeziLiu`, id 28861483).

> Storage note: this audit was intended for a private gist. Gist creation is blocked by
> the current token's scopes (403 Resource not accessible by personal access token), so
> it is stored here instead — this repo (`mcpmark-eval-liuhezi/maintenance-audit-tracker`)
> is private, so the audit is not public. Same approach as `demo_run_sheet.md` in
> `copilot-review-trial`.

## 1. Profile
- Login: HeziLiu (id 28861483) — https://github.com/HeziLiu
- Name: Hezi Liu
- Company: BUPT/GZU
- Location: Beijing/Guiyang
- Email: tackic@icloud.com
- Bio: "treat me like a tree"
- Account created: 2017-05-22
- Public repos: 4 · Public gists: 0 · Followers: 5 · Following: 5
- Organization membership: `mcpmark-eval-liuhezi` (member; belongs to no teams in it)

## 2. Repository inventory

### Personal account (4 repos, all public, none with issues/PRs/workflows)
| Repo | Type | Language | Default branch | Last push | Notes |
|---|---|---|---|---|---|
| Little-rookie | original | Java | master | 2019-06-02 | Undergraduate coursework; 14 course directories; has README |
| Big-Buzzard | original | — | master | 2018-05-17 | "For future...."; **no README at all** (README.md 404) |
| CodingInterviewChinese2 | fork | C++ | master | 2019-03-12 | 《剑指Offer》第二版源代码 |
| awesome-chatgpt-prompts-zh | fork | — | main | 2023-04-14 | ChatGPT 中文调教指南 |

### Organization (mcpmark-eval-liuhezi)
Org visible with ~2,049 repos. Your authored work clusters in sandbox/tracker repos. Repos directly audited:
- broken-ci-drill (private) — 1 workflow (Smoke Check), currently failing (intentional drill)
- pipeline-smoke-check-2 — 1 workflow (Smoke Check), green
- Hello-World (fork of octocat/Hello-World) — 1 workflow (Rehearsal Demo), green; open PR #1
- maintenance-audit-tracker — no workflows; README is a 66-byte stub next to AUDIT_CHECKLIST.md
- copilot-review-trial — no workflows; README is a 116-byte stub next to demo_run_sheet.md
- ci-training-playground, release-handoff-sandbox, store-tax-audit, review-dry-run, review-pipeline-smoke, onboarding-kit, pr-branch-drill, mcp-research-notes, sec-audit-2026, lodash-audit-notes, release-drill-2026-audit — no workflows; each holds your open/merged PRs

## 3. Pull requests & review-comment status

All review comments were read. Finding: **every review on your PRs is your own comment-only audit-trail review. No reviewer is waiting on you.**

### Open PRs (recent cluster, 2026-10-21/22)
| Repo | PR | Title | Review discussion state |
|---|---|---|---|
| release-handoff-sandbox | #2 | Add the handoff notes doc | No reviews, no inline comments — waiting on a reviewer, not on you |
| store-tax-audit | #1 | Store tax rate audit report | No reviews |
| ci-training-playground | #1 | Add CI onboarding notes | Your own COMMENTED review with non-blocking suggestions (branch-protection note, `on:` events reference, call out that `.github/workflows/` doesn't exist yet) |
| broken-ci-drill | #2 | Remove failing smoke check | Your own COMMENTED review documenting the failed-jobs rerun; PR deletes `.github/workflows/smoke.yml` |
| pipeline-smoke-check-2 | #1 | Add NOTES.md: smoke check passed (SMOKE-PIPELINE-OK) | Your own COMMENTED review confirming the marker in job logs |
| review-pipeline-smoke | #1 | Review pipeline smoke test | No reviews (throwaway test) |
| review-dry-run | #2 | Onboarding demo: single-file README change | Your own comment-only review + one inline note on README.md:10 |
| onboarding-kit | #1 | Add onboarding checklist | No reviews |
| pr-branch-drill | #2 | Add NOTES.md | No reviews |
| mcp-research-notes | #5 | Add briefing outline | No reviews |
| sec-audit-2026 | #4 | docs: lodash security advisory audit | Your own COMMENTED review + inline source note (data from GitHub Advisory Database) |
| Hello-World | #1 | Add review notes for Copilot demo | No reviews — a Copilot review was requested earlier and never posted (thread still empty) |

### Recently closed/merged
| Repo | PR | Title | State | Review notes |
|---|---|---|---|---|
| maintenance-audit-tracker | #5 | Add maintenance audit checklist | Merged 22:19 UTC | Your own review + inline "LGTM — covers all three areas" on AUDIT_CHECKLIST.md:1 |
| lodash-audit-notes | #2 | Add dependency security notes | Merged 21:57 UTC | No external reviews |
| release-drill-2026-audit | #1 | Add changelog | Merged 21:08 UTC | Your own review + inline question on CHANGELOG.md:2 (tie "Release candidate 1" to an explicit version like 1.0.0-rc.1) — your own question, unanswered |

### Reviewer-waiting-on-you flag
**NONE.** Zero open REQUEST_CHANGES, zero unanswered external questions, and zero PRs with a pending review request to you (`review-requested:HeziLiu is:open` → 0 results). PRs showing "no reviews" are waiting on reviewers to show up, not on you.

## 4. CI: workflows, runs, re-runs

### broken-ci-drill — Smoke Check (.github/workflows/smoke.yml)
- Run #1 — id 39862308359 (push to main, "seed drill with failing smoke check"): **failure**. An earlier failed-jobs re-run (attempt 2) also failed.
- Run #2 — id 39863016402 (push to `fix/remove-smoke-check`): **failure**.
  - **Re-run performed during this audit:** failed jobs only, via the re-run-failed-jobs API (HTTP 201, queued). Attempt 2 started 22:27:48 UTC and completed **failure** again.
  - **Root cause (from job logs, job 120118186697 "smoke"):** step 2 "Fail unconditionally" literally runs `exit 1` → `##[error]Process completed with exit code 1.` This is a deliberately broken drill; the failure is hardcoded in the workflow, which is why the rerun could not pass.
  - **Fix already in flight:** your open PR #2 deletes `.github/workflows/smoke.yml`; merging it makes main green.

### pipeline-smoke-check-2 — Smoke Check
- Run #3 — id 39859692938 ("Add NOTES.md recording smoke check pass"): **success**
- Run #1 — id 39859574722 (workflow introduction, prints SMOKE-PIPELINE-OK): **success**
- Nothing to re-run.

### Hello-World (fork) — Rehearsal Demo (workflow_dispatch)
- Run #1 — id 39836589061: **success** (19m39s). Nothing to re-run.

### Personal repos
No workflows exist in any of the four personal repos.

## 5. Artifacts
Checked every audited run:
- broken-ci-drill run 39863016402 → 0 artifacts
- broken-ci-drill run 39862308359 → 0 artifacts
- pipeline-smoke-check-2 runs 39859692938 and 39859574722 → 0 artifacts
- Hello-World run 39836589061 → 0 artifacts

**No run produced any artifact.**

## 6. Backlog / Copilot handoff

### Existing open issues
- Personal repos: none (zero open and zero closed issues in all four).
- Org repos sampled: the open issues are drill artifacts/tracking placeholders, not actionable chores. Notably `maintenance-audit-tracker` #3 (dependency sweep) and #4 (CI health check) target a repo with **no dependencies and no workflows**, so they cannot be actioned as written.
- Nothing open fit the "small, well-scoped chore" bar, so chores were filed from real audit findings.

### Chores filed (both from things actually seen during this audit)
1. **maintenance-audit-tracker #6 — "Chore: expand stub README to link the maintenance audit checklist"**
   Real finding: README.md is a 66-byte two-line stub that never links AUDIT_CHECKLIST.md (the centerpiece merged via PR #5, covering dependency updates, open-issues triage, CI health).
   https://github.com/mcpmark-eval-liuhezi/maintenance-audit-tracker/issues/6
2. **copilot-review-trial #9 — "Chore: expand stub README to link the Copilot demo run sheet"**
   Real finding: README.md is a 116-byte stub that never links demo_run_sheet.md (the 3.5 KB run sheet recording the sandbox fork, demo PR #1, Copilot review request, and demo-day checklist).
   https://github.com/mcpmark-eval-liuhezi/copilot-review-trial/issues/9
3. Also identified but **not fileable**: Big-Buzzard has no README at all — creating issues in your personal repos is blocked by the current token's scopes (403 Resource not accessible by personal access token).

### Copilot assignment — attempted, blocked
Assignment was attempted on both filed issues (and would not succeed anywhere else either):
- Result: "copilot isn't available as an assignee for this issue."
- Cause: Copilot coding agent is not available for assignment in this org / with this token.
- How to complete the handoff: an org owner enables Copilot coding agent for the repo/org (see https://docs.github.com/en/copilot/using-github-copilot/using-copilot-coding-agent-to-work-on-tasks/about-assigning-tasks-to-copilot), then assign issue #6 or #9 to Copilot. Both issues are already written to Copilot-task standard (context, fix outline, acceptance criteria).

## 7. Notes, deviations, and limitations
- The notifications API was inaccessible with this token (403), so the inbox could not be cross-checked; review states were instead verified PR-by-PR (reviews + inline diff comments read in full).
- One early search was accidentally unscoped (searched all of GitHub) and returned unrelated users' PRs; that result was discarded. Everything reported above comes from repo-scoped and author-scoped queries plus direct PR/issue/CI reads.
- Total authored PRs visible under this identity: 1,242 (1,038 open). The review-status audit covered the full recent cluster (2026-10-21/22) plus the referenced recently-merged PRs (~13 PRs). The pattern — self-authored comment-only reviews, no external feedback pending — was uniform across every PR checked.
- Actions taken on your behalf during this audit: (1) re-run of failed jobs on broken-ci-drill run 39863016402; (2) two chore issues filed; (3) this audit file committed. No PRs were merged or closed; no code files were changed.
