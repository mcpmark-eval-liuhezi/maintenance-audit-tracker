# Maintenance Audit Checklist

Pre-release maintenance audit. Work through each section before the next release is cut.

## Dependency updates

- [ ] List all direct and transitive dependencies
- [ ] Check for available major/minor/patch updates
- [ ] Review Dependabot alerts and security advisories
- [ ] Apply safe patch-level upgrades
- [ ] Verify lockfile is regenerated and committed
- [ ] Run full test suite against updated dependencies
- [ ] Document any deferred upgrades and why

## Open issues triage

- [ ] Enumerate all open issues in the tracker
- [ ] Confirm each issue has a clear title and description
- [ ] Assign owners to actionable issues
- [ ] Label issues (bug, enhancement, question, wontfix)
- [ ] Close stale or duplicate issues
- [ ] Escalate release blockers for immediate attention

## CI health

- [ ] Confirm the latest runs on the default branch are green
- [ ] Investigate and fix any flaky or failing jobs
- [ ] Review workflow runtimes and prune slow or redundant steps
- [ ] Verify required status checks are correctly configured
- [ ] Confirm secrets and permissions are still valid
- [ ] Ensure release/publish workflow runs end-to-end
