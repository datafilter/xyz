# Design Goals

## Content in Plain Markdown

- Accessible without JavaScript.
- Easier to edit, parse, index, and search.

## Tags as Metadata in Markdown

- Tags provide a quick summary of the content.
- They can be used as search keywords.

## Dynamic site from content

- Preview instantly available on git push
- Published blogs updated not long thereafter

## Minimal

- No frameworks
- No slow build times
- Vanilla js, no embrace-extend-extinguish corporation languages here.

# V2

_Benched goals, only relevant if this was a high traffic site_

## Static Build Output

- Faster load times.
- Less client-side compute.

## Incremental Builds

- Gather metadata and build only for files that have changed.
  - Quicker deployment.
  - Reduces server-side re-computation.

## Unrelated Metadata Separate from Content

- Metadata (Where or when) independent from the content, as metadata is only relevant to pages that reference the conent.
- Ideally, metadata is extracted at build time, rather than included in content.
