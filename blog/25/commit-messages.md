<!-- md.1
published @2025-03-03
updated @2025-03-27
changelog
naming
git
—-->

# Semantic Commit Prefixes

## Common Git commit practices

It helps when commits are short and focused. The smaller a change, the easier it is to review and revert.

The more frequent you commit, the easier it is to go back to a working state without losing a lot of work.

Atomic (or self-contained) commits focus on a single change. They are easy to revert in isolation.

## Naming things

Meaningful commit messages guidelines:
* Keep the subject line short and descriptive
* Focus on the “What” and only if necessary, the "Why"
* Write in the imperative mood e.g., 'Fix bug' rather than 'Fixed bug'
* Optionally, reference a task to:
   * provide additional context in the future
   * related tickets are closed automatically


## Git Karma

Sometimes, you'll come across commit messages that start with "Add" "Bump" "Test" or "Chore"

Recently I've come across a commit style that defines specific prefixes, called [Git Karma Style](https://karma-runner.github.io/6.4/dev/git-commit-msg.html)
which might have started [as this gist](https://gist.github.com/fil-lewis-barclay/746e7563808d38400b89).


They structure commit messages in the format:
```
  <type>(<scope>): <subject>
```
- **Type** indicates the category of change, such as a new feature or bug fix.
- **Scope** the section, component, or area affected.
- **Subject** is a brief description

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

I find this commit message structure useful:
```
  <type>(<context>): <summary>
```
- **Type** indicates the motivation or cause
- **Context** gives any helpful context, such as the reason for the change or which aspect changed.
- **Summary** is a brief description

Preferred `<type>` values: feat, fix, tidy, build, edit

### Context instead of Scope

Which things have changed is already apparent via source control.

I prefer additional information about _why_ things have changed rather than _how_. Specifically, when reviewing code, I'd like to know which commits change **behavior**, i.e., _feat_ or _fix_.

Therefore instead of `<scope>` I chose `<context>`, for example:

`fix(perf): Use standard quicksort instead of custom logic`

### 5 types instead of 9

- Sometimes changes dont fit exactly into one of the 9 categories.
- I don't like the friction of over-classifying what I've done,
- nor do I find all 9 scopes particularly useful when reviewing changes.

I've settled on only these five `<type>` values for now:

### Things That Change Behavior
- **feat:** New features.
- **fix:** Adjustments that align unintended behavior with expectations.
```
feat(auth): Add OAuth2 login support
fix(login): Correct validation error message
```
### Things That Don't Change Behavior
- **tidy:** Clarifying intent — tests, refactoring, documentation, styling improvements, etc..
- **build:** Updates in CI/CD, config, infrastructure, compilation, containerization, or dependency bumps.
```
tidy(docs): Update README for installation instructions
build(ci): Update GitHub Actions workflow for deployment
```
### Anything Else
- **edit:** A general catch-all that doesn't neatly classify as feat, fix, tidy & build.
```
edit(assets): Remove unused icons
```

## Pros and Cons

**Pros:**

- Distinguishes feature changes from internal improvements. This highlights commits for functional changes, and reviewers can skim over those that don't.
- Helps with automated changelog generation.

**Cons:**
- Can introduce a slight barrier towards smaller commits.
- Less characters available for the actual commit description.

## Wrap up

While semantic prefixes aren’t a one-size-fits-all solution, I hope you found these ideas interesting. I'll continue experimenting with my approach and update here if I discover something better.
