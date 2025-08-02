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
> a brief summary of the change

e.g.
```
Update database query logic for performance improvement
Prevent buffer overflow in user profile module
```

But which commits are the most important to pay attention to?

---

## Context

Which things have changed is already apparent via source control.

To highlight what the commit is _about_, add `type` and/or `context`:
```
type: description

or

type(context): description
```

### `type`
> the motivation or cause of the change.
### `context`
> optional extra info, such as the reason for the change or which aspect changed.

---

## Type of change

For `type` use of `feat`, `fix`, `tidy`, `build` or `edit`. 

### things that change behavior:
- **feat:** New features.
- **fix:** Adjustments that align behavior with expectations. _(old or new)_
```
feat(auth): Add OAuth2 login support
fix(login): Correct validation error message
```
### things that do not change behavior:
- **tidy:** Clarifying intent — tests, refactoring, documentation, styling improvements, etc..
- **build:** Updates in CI/CD, config, infrastructure, compilation, containerization, or dependency bumps.
```
tidy(docs): Update README for installation instructions
build(ci): Update GitHub Actions workflow for deployment
```
### anything else
- **edit:** A general catch-all that doesn't neatly fall into feat, fix, tidy or build.
```
edit(assets): Remove unused icons
```
You can of course use whatever you like for `type`, but it's easier when you have fewer options to pick from. 

Often what matters most when you review a change, or large set of changes, is whether a commit changes behavior of the code or not.

## Pros and Cons

**Pros:**

- Easier code reviews. You get a birds-eye-view just from the commit messages page alone, and know where to focus on the most relevant changes.
- Messages more likely describe _why_ things have changed, instead than _how_.
- Distinguishes feature/functional changes from internal improvements.
- More context in git blame when following the history of a change.
- Helps with automated changelog generation.

**Cons:**
- Introduces a slight barrier towards smaller commits if you _have_ to classify each commit.
- Less characters available for the commit description.

## Related work

Because of the extra friction to come up with commit messages, I don't think you need to be strict about it or follow the practice on every commit. Instead of reviewing large commits, I'd rather review lots of tiny commits in a PR/MR with good enough names.

But, if you want more formal, rigid structure, there are conventions like:

* [Karma's commit message conventions](https://karma-runner.github.io/6.4/dev/git-commit-msg.html), which might have started [as this gist](https://gist.github.com/fil-lewis-barclay/746e7563808d38400b89)

* [Conventional Commits](https://www.conventionalcommits.org/)


## Wrap up

A little bit of extra context goes a long way. It might seem excessive at first, but try it out for a week — it's not _that_ much effort, and it can be quite useful in a team setting and/or over the long term.
