# Website Content

Edit **index.md** to update the homepage. The HTML layout, photo, and responsive columns stay in **index.html**; appearance is controlled by **style_redeisgned.css**. The CV and other pages are unchanged.

## Editing

- The first block contains the bio and profile links.
- Updates follow `<!-- updates -->`. Keep them newest first.
- Publications follow `<!-- publications-and-projects -->` and appear in the right column.
- Projects follow `<!-- projects -->` and appear below Updates in the left column.
- Keep all three section markers unchanged and present exactly once. On mobile, the order is Updates, Projects, then Publications.
- Separate entries with `---` on its own line, with blank lines above and below.
- Use `#### Title` for an entry title, `**Name**` for bold text, and `[Link text](https://example.com)` for links.
- Lines like `{: .venue}` or `{: #emnlp-2025}` set styling or link targets. Keep them immediately below the paragraph or heading they apply to.
- Keep `<time datetime="2026-10-11">11 October 2026</time>` for accessible dates. Use only a year or year-month when no precise date is known.
- The section headings and your name are in the HTML layout; do not repeat them in Markdown.

### Add an Update

Copy an existing entry to the top of the Updates block, then change its date and text:

```markdown
<time datetime="2026-10-11">11 October 2026</time>

Your update text, with an optional [link](https://example.com).

---
```

### Add a Publication

Copy an existing publication and edit the title, authors, venue, date, and link. Place it before the full publication list link. Use factual information only.

```markdown
#### [Publication Title](https://example.com/paper)

Author names, including **McGill, E.**
{: .authors}

*Venue name*, <time datetime="2026">2026</time>.
{: .venue}

---
```

Projects use the same heading/link pattern, followed by a description, and do not need author or venue lines.

## GitHub Pages

This homepage requires Jekyll processing. In the repository's **Settings > Pages**, a **Deploy from a branch** source using the repository root runs GitHub Pages' built-in Jekyll build. Commit and push the HTML, Markdown, stylesheet, and `_config.yml` together. No local installation is required for that deployment method.

If Pages uses a custom GitHub Actions workflow, it must build with Jekyll before uploading the site; uploading the raw repository alone will not render the Markdown. A `.nojekyll` file must not be present for the built-in Jekyll build.

`index.md` is deliberately excluded as a standalone page: `index.html` includes its source and renders the four blocks using Jekyll's `markdownify` filter. This avoids two files generating the same homepage URL.

VS Code's Markdown preview can show the editable content, but not the complete website layout. Opening `index.html` directly no longer renders the complete page. Use the published site, or an optional local Jekyll build, to preview the final design.