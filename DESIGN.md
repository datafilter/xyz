# Design Goals

## Content in Plain Markdown

- Accessible without JavaScript.
- Easier to edit, parse, index, and search.

## Tags as Metadata in Markdown

- Tags provide a quick summary of the content.
- They can be used as search keywords.

## Irrelevant Metadata Separate from Content

- The context of where or when content exists is relevant to pages that reference it, but not to the content itself.
- Ideally, this metadata should be extracted at build time rather than included in the content's markdown.

## Static Build Output

- Improved SEO.
- Faster load times.
- Minimizes duplicated compute, to save some energy and battery life.

## Incremental Builds

- Gather metadata and build only for files that have changed.
  - Quicker deployment.
  - Reduces wasted computation.

