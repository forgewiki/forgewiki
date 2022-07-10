# Markdown Style Guide

The Forge Wiki supports the [<mark style="color:blue;">**Markdown Markup Language**</mark>](https://en.wikipedia.org/wiki/Markdown) <mark style="color:blue;">****</mark> (you can also find a "Cheatsheet" <mark style="color:blue;">****</mark> [<mark style="color:blue;">**here**</mark>](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)).

Markdown can be written in various different styles, in this document you will find the standard formatting guide for creating Forge Wiki documentation.

### Rules

#### MD001 - Header levels should only increment by one level at a time

Headers should not be skipped, instead incremented one by one.

**Wrong:**

```markdown
# Header 1

### Header 3

We skipped out a 2nd level header in this document
```

**Correct**:

```markdown
# Header 1

## Header 2

### Header 3

#### Header 4

## Another Header 2

### Another Header 3
```

### MD002 - First header should be a top level header

The first header of the document should be a top level header (H1).

**Wrong**:

```
## This isn't a H1 header

### Another header
```

**Correct**:

```
# Start with a H1 header

## Then use a H2 for subsections
```
