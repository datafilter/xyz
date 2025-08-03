<!-- md.1
published @2025-03-03
updated @2025-08-02
changelog
naming
git
—-->

# Contextual Commit Prefixes

## Relevance

Commit messages communicate the intent of a change.

### `description`
> A brief summary of the change.

e.g.
```
Improve database query for performance
Prevent buffer overflow in user module
```

But which commits are the most important to pay attention to?

---

## Context

What has changed is already apparent via source control.

To highlight what the commit is _about_, add `type` and `context`:
```
type: description

or

type(context): description
```

### `type`
> The motivation or cause of the change.
### `context`
> Optional extra info, such as the reason for the change or which aspect affected.

---

## Type of change

Use `type` to indicate: `feat`, `fix`, `tidy`, `build` or `edit`. 

### Commits that change behavior:
- **feat:** New features.
- **fix:** Adjustments that align behavior with expectations. _(old or new)_
```
feat(auth): Add OAuth2 login support
fix(login): Correct validation error message
```
### Commits that do not change behavior:
- **tidy:** Clarifying intent — tests, refactoring, documentation, styling improvements, etc..
- **build:** Updates in CI/CD, config, infrastructure, compilation, containerization, or dependency bumps.
```
tidy(docs): Update README for installation instructions
build(ci): Update GitHub Actions workflow for deployment
```
### Anything else:
- **edit:** A general catch-all that doesn't neatly fall into feat, fix, tidy or build.
```
edit(assets): Remove unused icons
```
You can use whatever you like for `type`, but having only a few options makes it easier to pick a `type` for the commit.

Often, the important aspects during review — especially for large sets of changes — is whether the commit alters code behavior or not.


## Pros and Cons

**Pros:**

- Easier code reviews. You get a birds-eye-view just from the commit messages page alone, and know where to focus on the most relevant changes.
- Messages are likely to also describe _why_ things have changed.
- Distinguishes functional changes from internal improvements.
- Helps with automated changelog generation.
- More context in git history.

**Cons:**
- Introduces a slight barrier to smaller commits, if each commit has to be classified.  
- Fewer characters available for the commit description.


## Related work

If the extra friction of classifying commit messages leads to fewer, larger commits, it's better to avoid this practice for every commit.

Having many small commits in a PR/MR - with good enough names but without a contextual prefix - is preferable to large commits all prefixed with `feat` or `fix`.

If you want a more formal, rigid structure, there are conventions like:

* [Karma's commit message conventions](https://karma-runner.github.io/6.4/dev/git-commit-msg.html), which might have started [as this gist](https://gist.github.com/fil-lewis-barclay/746e7563808d38400b89)

* [Conventional Commits](https://www.conventionalcommits.org/)


## Wrap up

A little bit of extra context goes a long way. It might seem excessive at first, but try it for a week — it's not _that_ much effort, and it can be quite useful in a team setting and over the long term.
