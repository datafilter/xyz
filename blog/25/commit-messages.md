<!-- md.0
published @2025-03-03
changelog
naming
git
—-->

# Git Commit Labels

> TLDR: Short prefixes in git commit messages to highlight functional changes. It makes code reviews both quicker and more thorough where it matters; as it pinpoints to where behavior shifted. A few seconds for a little bit of extra context goes a long way.

For over a year now, I’ve been prefixing my commit messages with simple labels. Just a quick "what is this" marker:

```
feat: add OAuth2 login support
fix: correct validation error on signup
tidy: replace configuration as code with config file
test: add edge case for invalid token
```

## Motivation

The value isn't in the categorization itself; it’s in the signal-to-noise ratio.
When scanning a PR or a long git log, you want to know what actually changes the system. By using Git Commit Labels, behavior-changing commits jump out immediately:

`feat` – New behavior.

`fix` – Behavior corrected (aligning it with expectations).

Everything else is usually "noise" when you're debugging or reviewing. Whether it's a [tidy](https://kentbeck.com) (refactor/cleanup) or a test, you know at a glance that these shouldn't be the cause of a new bug or a functional shift.

## Labels I typically use

I found that sticking to a few options makes the overhead of choosing a label almost zero:
```
feat / fix: The "important" ones. Pay attention here.
tidy: Anything that makes intent more apparent or the codebase easier to modify
test: New or updated tests.
```

Sometimes I'll use other labels like:
```
build : CI/CD, dockerfile or compiler options
bump: Upgrading dependencies
perf: Performance improvements
infra: Infrastructure-as-code changes
docs: Documentation, sometimes even for tests
edit: Miscellaneous, eg. removing unused assets
```

It's not an exhaustive list, and again, my emphasis is largely on `feat` & `fix`. With `feat` I don't mean a _new_ feature per say, or that the change was a great feat 🏋️ - just that some `aspect` or `property` changed - maybe I'll replace my wording of `feat` with `mod` in the future 🤔

## Why not go "Official"?

You may have seen [Conventional Commits](https://www.conventionalcommits.org/) or the [Karma style](https://karma-runner.github.io/6.4/dev/git-commit-msg.html). In my experience the value proposition quickly drops off with rigid labels and parenthesized or scopes.
- You don't gain much, and they often re-state the same thing you can derive from the commit message and the files that were changed.
- When you're making tiny, rapid-fire commits, stopping to classify them can feel like a speed bump.

I prefer a more lightweight approach. It’s less about following a strict spec and more about providing a "bird's-eye view".

# Wrap up

Try it for a week. Don’t get hung up on the "perfect" label — just start using `feat:`

Once you get used to it, you’ll find it’s worth the few extra seconds.

Big thanks to [Diogo](https://github.com/diogoaurelio/actionoscope/commits/main/) who introduced me to this style!
