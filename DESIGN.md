# Design Goals

## Content in Plain Markdown

- Accessible without JavaScript.
- Easier to edit, parse, index, and search.

## Tags as Metadata in Markdown

- Tags provide a quick summary of the content.
- They can be used as search keywords.

## Irrelevant Metadata Separate from Content

- Metadata (Where or when) independent from the content, metadata is only relevant to pages that reference the conent.
- Ideally, metadata should be extracted at build time rather than included in content markdown.
https://github.com/datafilter/xyz/blob/main/blog/25/commit-messages.md

## Static Build Output

- Improved SEO.
- Faster load times.
- Minimizes duplicated compute.

## Incremental Builds

- Gather metadata and build only for files that have changed.
  - Quicker deployment.
  - Reduces wasted computation.

