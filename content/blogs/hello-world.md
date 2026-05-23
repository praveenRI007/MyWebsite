---
title: "Hello, World — first post"
date: 2026-05-22T10:00:00+01:00
draft: false
tags: ["meta", "intro"]
categories: ["general"]
author: "Praveen Rajendran"
description: "Kicking off the blog — what this site is for, and what's coming."
cover:
  image: "/images/blogs/hello-cover.jpg"   # put a JPG/PNG with this name under static/images/blogs/
  alt: "Cover image"
  caption: "Cover image"
  relative: false
  hidden: false
ShowToc: true
TocOpen: false
---

This is the very first post on **Praveen's Workspace**. I'll use this
space to write about ML, causal inference, RL experiments, and the
occasional non-technical thing.

## Why a blog?

Writing forces clarity. If I can't explain it, I haven't understood it.

## Adding images

You can drop images into `static/images/blogs/` and reference them like
this:

![A descriptive alt text](/images/blogs/example.jpg)

Or with a caption using a figure:

{{< figure src="/images/blogs/example.jpg" alt="alt text" caption="A caption goes here" >}}

## Code blocks

PaperMod gives you syntax highlighting and a copy button automatically:

```python
def hello(name: str) -> str:
    return f"Hello, {name}!"

print(hello("world"))
```

## Math (optional)

If you want LaTeX math, PaperMod doesn't ship it by default — enable
KaTeX/MathJax via a custom partial later when you need it.

---

That's it for now. More posts coming.
