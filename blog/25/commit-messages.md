<!-- md.1
published @2025-03-03
updated @2025-03-03
changelog
practices/git/naming/commit
—-->

# Semantic Git Commit Prefixes

## Common Git commit practices

It helps when commits are short and focused. The smaller a change, the easier it is to review and revert. The more frequent you commit, the easier it is to revert current changes back to a working state without losing a lot of work.

Atomic (or self-contained) commits focus on a single change. This helps reviewers concentrate on commits that change functionality while quickly skimming over those that don't.

## Naming things

Meaningful commit messages are:
* Keep the subject line short and descriptive
* Write in the imperative mood (e.g., 'Fix bug' rather than 'Fixed bug')
* Reference issues or tasks - _typically not necessary in commit messages themselves_

Sometimes, commit messages might start with "Add" "Bump" "Test" or "Chore".

## Git Karma

Recently I've come across a commit style that defines specific prefixes, called [Git Karma Style](https://karma-runner.github.io/6.4/dev/git-commit-msg.html)
which might have started [as this gist](https://gist.github.com/fil-lewis-barclay/746e7563808d38400b89).


They which structures commit messages in the format:
```
  <type>(<scope>): <subject>
```
- **Type** indicates the category of change, such as a new feature or bug fix.
- **Scope** specifies a section, component, or area of the code that is affected.
- **Subject** is a brief description of the commit in imperative mood (e.g., "Fix bug" rather than "Fixed bug").

~~Allowed*~~ *_[Recommended](https://github.com/karma-runner/karma/commits/master
)_ `<type>` values: feat, fix, perf, docs, style, refactor, test, build, _chore_

Some examples:

```
fix(middleware): ensure Range headers adhere more closely to RFC 2616
build(deps-dev): bump ws from 6.2.1 to 6.2.3
fix: add build commits for patch release
docs: Add deprecation notice to Karma README
```

## My take on contextual git prefixes

I don't always make a change that fits exactly into one of the 9 categories, and I don't like the pause of over-classifying what I've done, nor do I find them particularly useful when reviewing changes.

I've reworked and grouped the categories, and these are the five `<type>` values I've settled on for now:

### Things That Change Behavior
- **feat:** For new features that change behavior.
- **fix:** For bug fixes and adjustments that align unintended behavior with expectations.
```
feat(auth): Add OAuth2 login support
fix(login): Correct validation error message
```
### Things That Don't Change Behavior
- **tidy:** For changes that improve clarity—refactors, documentation, styling improvements, and tests.
- **build:** For updates in CI/CD, infrastructure, compilation, containerization, or dependency bumps.
```
tidy(docs): Update README for installation instructions
build(ci): Update GitHub Actions workflow for deployment
```
### Anything Else
- **edit:** A general catch-all that doesn't neatly classify as feat, fix, tidy & build.
```
edit(scripts): Remove unused assets
```

### ~~Scope~~ Context

I don't regard the information in the `(<scope>)` segment as a strict requirement to denote a component. It's something optional anyway.

Instead, including a reason or context is more informative, for example:

`fix(perf): Use standard quicksort instead of custom logic`

## Pros and Cons

**Pros:**

- Distinguishes feature changes from internal improvements.
- Helps with automated changelog generation.

**Cons:**
- Can introduce a slight barrier for smaller commits.
- Less characters available for the actual commit description.
- Not every change may always neatly fit into a predefined category.

## Wrap up

While semantic prefixes aren’t a one-size-fits-all solution, I hope you found these ideas interesting. I'll continue experimenting and update this blog if I discover something better. 
