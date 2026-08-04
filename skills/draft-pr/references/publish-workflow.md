# Publication Workflow

Read this before mutating Git state or creating or updating a GitHub PR. The
user must already have requested publication or an existing PR update.

## Contents

- Preflight
- Base and existing PR
- Commit and push
- Create or update the PR

## Preflight

```bash
gh --version
gh auth status
implementer_login="$(gh api user --jq '.login')"
git rev-parse --show-toplevel
git status -sb
git branch --show-current
git remote -v
```

Stop if `gh` is missing or unauthenticated. Do not silently switch to a
lower-confidence publication path. If the login lookup fails, leave assignees
unchanged and report that separately from the PR result.

If the current branch is the remote default branch, create a descriptive topic
branch without a model or agent prefix.

## Base And Existing PR

Prefer the user's explicit base. Otherwise, reuse an existing PR's base:

```bash
gh pr view --json number,url,title,body,baseRefName,isDraft,state,assignees
```

If no PR exists, query the remote default:

```bash
gh repo view --json defaultBranchRef --jq '.defaultBranchRef.name'
```

Fetch the selected publication remote before comparing or publishing. Rebase
only when the topic branch is behind, conflicted, or explicitly needs sync:

```bash
git fetch <remote>
git rebase <remote>/<base-branch>
```

Resolve conflicts intentionally, run focused checks, stage only resolved files,
and continue. Abort when a safe resolution requires product judgment the user
has not supplied. Use a merge commit only when the repository requires it or
the user asks for one.

## Commit And Push

Inspect the diff and commit only the intended scope:

```bash
git diff --stat
git diff
```

Stage explicit paths when unrelated changes exist. Use `git add -A` only when
the entire worktree belongs to the PR. Push a new or unchanged topic branch
with `git push -u <remote> HEAD`. After rebasing an already-pushed, clearly
user-owned topic branch, use `git push --force-with-lease`; ask before rewriting
a shared or ambiguous branch.

## Create Or Update The PR

Write real Markdown to a temporary file and use `--body-file`. Do not rely on
`--fill` or a multiline `--body` argument for final content.

```bash
tmp_pr_body="$(mktemp -t draft-pr-body.XXXXXX.md)"
```

Create a new draft:

```bash
pr_ref="$(gh pr create --draft --base "<base-branch>" --head "$(git branch --show-current)" --title "<concise title>" --body-file "$tmp_pr_body")"
```

Update an existing PR without changing its title unless requested:

```bash
pr_ref="<number>"
gh pr edit "$pr_ref" --body-file "$tmp_pr_body"
```

After the create or update succeeds, clean up the temporary file and add the
authenticated user without removing existing assignees:

```bash
rm -f "$tmp_pr_body"
gh pr edit "$pr_ref" --add-assignee "$implementer_login"
```

Assignment failure does not invalidate a successful PR create or update. Report
it separately. Verify the remote result rather than trusting command success:

```bash
gh pr view "$pr_ref" --json number,url,title,body,baseRefName,headRefName,isDraft,state,assignees
```
