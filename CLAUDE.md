# CLAUDE.md

- **Open a pull request; `master` is protected.** A direct push is rejected rather than queued, so branch, push the
  branch and open the PR with `gh pr create`. What the protection requires is deliberately not restated here, read it
  from `gh api repos/{owner}/{repo}/branches/master/protection` and `gh api repos/{owner}/{repo}/rulesets`, either of
  which may be the one in force. The approval comes from Claude, which the organization's `Common workflows` ruleset
  runs on a pull request into `master` — nobody here can approve their own. So open it ready for review rather than as a
  draft: a draft gets no review, and marking it ready starts none, so the approval it needs waits for its next push.
- **A pull request is not done when it is opened.** It is reviewed automatically, and again on every push, so each fix
  can draw new feedback. Watch it after submitting, and keep addressing the reviews and failing checks until it merges.
- **Ask whether a pull request should merge itself.** `gh pr merge --auto --squash` hands it to GitHub, which merges the
  moment the checks pass and the review approves — with nobody looking at it again. That is the user's call rather than
  a default to assume either way, so when they have not said, ask before opening it, and leave auto-merge off until they
  answer.
