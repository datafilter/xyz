<!-- md.1
draft true
# published @2025-02-23
# updated @2025-02-23
changelog
practices/code/naming/git/commit
—-->

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

https://gist.github.com/fil-lewis-barclay/746e7563808d38400b89
https://karma-runner.github.io/6.4/dev/git-commit-msg.html

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

Enumerate & Group:

..todo

feat: something new
fix:
tidy: refactor, docs
build: cicd, ias, compilation & containerization
edit: catch-all for changes

# Conclusion/Alternative:

I'm still experimenting with what might work for me or not. I'm considering going with something like

intent(scrope)

That serves to show the why behind the what, and not just the what behind the what.
