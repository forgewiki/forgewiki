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
