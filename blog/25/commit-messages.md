<!-- md.1
draft true
# published @2025-02-23
# updated @2025-02-23
changelog
practices/code/naming/git/commit
—-->

> Remove all of this with a much shorter blog, about git top conventions, and how contextual prefixes (like git karma) can be useful.

# Into - Commit messages

Common conventions in commit messages are: 
Atomic
Small
Present tense active voice

Optionally, start with a ticket number to some work tracking system
example - `BLAH-334 Do something`
Sometimes useful. Not required when using GitHub/Tea/Lab(replace to include CodeBerg) issue numbers in PR, still easily discoverable via UI.

# Commit log

On one of the changelogs of one of my projects on a CHANGELOG.MD I chose to define a _change type_ for each entry.

Although it didn't start out like it, the idea behind the types eventually became

## feature
 Something new is available for the user
## fix
 Unexcepted or flawed behavior was fixed. 
## performance
 It's faster now. 
## maintenance
 Some routine work was done, like upgrading a development dependency like a linter, GitHub action, tool version etc.

 The idea was that the first 2 things would be interesting to the consumer: new features, bug fixes. The last two things were just informational - why the version was bumped.

# Karma-style commit messages

Recently I learned about a commit style for Karma:

The reasons for these conventions: #
automatic generating of the changelog
simple navigation through git history (e.g. ignoring style changes)
Format of the commit message: #
<type>(<scope>): <subject>

https://gist.github.com/fil-lewis-barclay/746e7563808d38400b89
https://karma-runner.github.io/6.4/dev/git-commit-msg.html

feat (new feature for the user, not a new feature for build script)
fix (bug fix for the user, not a fix to a build script)
perf ( for performance improvements. Such commit will trigger a release bumping a PATCH version.)
docs (changes to the documentation)
style (formatting, missing semi colons, etc; no production code change)
refactor (refactoring production code, eg. renaming a variable)
test (adding missing tests, refactoring tests; no production code change)
chore (updating grunt tasks etc; no production code change)
build ( for updating build configuration, development tools or other changes irrelevant to the user.)

The contributors don't strictly adhere to themselves, it's a bit inconsistent: 
https://github.com/karma-runner/karma/commits/master

# Pros and cons

## Pro's
Easy to review
Refactoring separated from changes

## Con's
 isn't always clear
Barrier to smaller commits
* longer commit messages
* not all changes might fit neatly into to-do: reference other blog about real world categories

# New approach?

Explain the intent of fewer categories, and how it addresses the above problems

Suggested intents:

## things that change behavior
feat: new feature,
fix: change unintended behaviour to align with expectations, bugfix, etc.

## things that doesn't change behavior
tidy: make the code easier to understand: refactor, docs, style, test
build: cicd, ias, compilation & containerization, bump dependencies
edit: catch-all for changes

Suggested ~scopes~ intent:

perf: performace code can be a tradeoff at the cost of readability, a perf commit can help find the og code and explain the way it is

eg, edit(perf): Replace recursive call with loop

---

### Things That Change Behavior

1. **feat**: New feature
   - `feat(auth): Add OAuth2 login support`
   - `feat(ui): Implement dark mode toggle`
   - `feat(api): Introduce new endpoint for user profiles`

2. **fix**: Change unintended behavior to align with expectations, bugfix, etc.
   - `fix(login): Correct validation error message`
   - `fix(cart): Resolve issue with item quantity not updating`
   - `fix(api): Fix 500 error on user data retrieval`

### Things That Don't Change Behavior

1. **tidy**: Make the code easier to understand: refactor, docs, style, test
   - `tidy(docs): Update README for installation instructions`
   - `tidy(style): Standardize code formatting with Prettier`
   - `tidy(tests): Improve test coverage for user service`

2. **build**: CI/CD, infrastructure as code, compilation & containerization, bump dependencies
   - `build(ci): Update GitHub Actions workflow for deployment`
   - `build(container): Optimize Dockerfile for smaller image size`
   - `build(deps): Upgrade React to version 17.0.2`

3. **edit**: Catch-all for changes
   - `edit(config): Adjust configuration settings for staging environment`
   - `edit(scripts): Remove unused build scripts`
   - `edit(notes): Add comments to clarify complex logic`

### Additional Examples
- `feat(notifications): Add email notifications for user sign-up`
- `fix(api): Fix incorrect response format for user data`
- `tidy(components): Refactor button component for better reusability`
- `build(deps): Bump lodash to version 4.17.21`
- `edit(assets): Update logo image for branding consistency`

# Conclusion/Alternative:

I'm still experimenting with what might work for me or not. I'm considering going with something like

intent(scrope)
or context(reason)
or ?

That serves to show the why behind the what, and not just the what behind the what.
