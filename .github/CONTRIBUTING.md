# Contributing

Thanks for your interest in contributing to Esploated! Please take a moment to review this document **before submitting an issue or pull request**.

## Issues

The simplest way to contribute is to [create an issue](https://github.com/cossssmin/esploated/issues/new) - you only need a GitHub account.

An issue template is provided, so you only need to replace the text in `[brackets]`.

For the issue title, please follow the suggested format:

```
[ESP NAME]: [ISSUE]
```

For example:

```
Mailchimp: duplicated media queries
```

## Pull Requests

Open a pull request to add an ESP or an ESP bug.

### Adding ESPs

ESPs are listed in alphabetical order in [`providers.json`](https://github.com/cossssmin/esploated/blob/master/providers.json).

When adding an ESP, please make sure to:

1. Add their website URL
2. Spell their name correctly
3. Insert the entry at the correct (alphabetical) position

### Adding bugs

Each ESP bug has a corresponding `.md` file inside the `content/[esp]/` folder. 

For example, `content/campaign-monitor/auto-paragraphs.md`:

> Note: make sure your file name is concise.

```md
---
esp: "Campaign Monitor"
title: "Text editor automatically adds paragraphs"
description: "The rich text editor in Campaign Monitor adds paragraph tags when hitting Enter"
fixed: "n/a"
date: 2020-01-16 13:20:43
author: ['John Doe', 'https://example.com'] 
tags: ['campaign-monitor', 'editor']
---

## Issue

Campaign Monitor's rich text editor automatically inserts `<p>` tags in `<multiline>` editable text areas.

Depending on where you're using `<multiline>`, this can result in invalid HTML or unexpected text formatting.

## Solution

Make sure to use `<multiline>` only where `<p>` tags would normally be output in your code.

Alternatively, you can click the `<> Source` button in the editor and manually remove the `<p>` tags surrounding your text.
```

As you can see, an `.md` file starts with a YAML Front Matter block:

- `esp` : the name of the ESP, exactly as in the `providers.json` file
- `title` : short description of the bug, used as the page title
- `description` : longer, used as the page meta description
- `fixed` : is it fixed by the ESP? Can be `true`, `false`, or `"n/a"` if it's just an annoying _feature_
- `date` : when was this file last updated, in `YYYY-MM-DD HH:mm:ss` format
- `author` : who submitted this issue? Can be `string` or `array`:
    - `"John Doe"` - just your name
    - `['John Doe', 'https://example.com']` - your name linked to your website
- `tags` : array of up to 3 relevant tags, in `kebab-case`

Then, we describe the problem under `## Issue`. If there's a way to fix it, we write it under `## Solution` (otherwise write `N/A`).