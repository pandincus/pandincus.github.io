---
title: "Hello, Journal"
date: 2026-07-28
tags: ["meta", "getting-started"]
cover:
    image: "placeholder.svg"
    alt: "A placeholder screenshot"
    caption: "Swap this for a real screenshot from whatever you're playing"
---

This is the first entry. Not much to say yet — just proving the format works: a post
lives in its own folder, images sit right next to the Markdown file, and everything
ships together when you push.

## How this works

Every post is a folder like this one (`content/posts/my-first-entry/`) containing an
`index.md` and whatever images or GIFs go with it. Drop a screenshot in the same
folder and reference it like this:

{{< figure src="placeholder.svg" alt="Placeholder screenshot" caption="Here's how a screenshot with a caption looks." >}}

GIFs work exactly the same way — just drop a `.gif` file in the folder and reference
it the same as a PNG or JPG.

## The in-character bit

Sometimes a moment in a game hits and it's worth writing from inside it:

> *The signal's been dead for six hours. Either the relay's down, or nobody's left to
> hold it.* — some character, probably, thinking something, at some point

And sometimes it's just mechanics — a build that finally clicked, a boss fight that
took nine tries, whatever's worth remembering.

## Publishing

Writing a new entry is:

```bash
hugo new content posts/whatever-you-want/index.md
```

Then drop images into that folder, write the post, `git add`, `git commit`, `git push`
— GitHub Actions builds and deploys it automatically.
