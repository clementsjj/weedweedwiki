---
title: Editing Guide
description: Hugo shortcodes and formatting reference
draft: false
date: 2026-02-03
---

This site is created using Hugo. When writing pages, there are certain Hugo "shortcodes" that can be used to inject HTML components.

## Article Frontmatter

These are the variables that can be provided in frontmatter on each page:

```yaml
---
title: <Page Title>
description: <Page Description>
draft: false
date: 2026-01-11
lastmod: 2026-01-17
toc: false           <------------Defaults to True; Setting to false will remove the sidebar toc.
categories:
  - <Category Tag>
related:
  - <Related Page 1>
  - <Related Page 2>
aliases:
  - /alternate-url/
---
```

## Shortcodes

### toc

This adds a table of contents next to the infobox, in the main/first paragraph of a page. 
This is useful to fill whitespace. 
If using this shortcode, it is helpful to set `toc: false` in the frontmatter of the page.

{{< details summary="Shortcode Example" >}}
<pre><code>&#123;&#123;&lt; toc &gt;&#125;&#125;</code></pre>
{{< /details >}}

### infobox

Creates a Wikipedia-style infobox that floats to the right of the content.

{{< details summary="Variables" >}}
- title
- image
- caption
{{< /details >}}

{{< details summary="Shortcode Example" >}}
<pre><code>&#123;&#123;&lt;infobox
    title="Cannabis sativa"
    image="https://upload.wikimedia.org/wikipedia/commons/a/a8/Cannabis_leaf.svg"
    caption="A flowering cannabis plant"
&gt;&#125;&#125;

| Field | Value |
|-------|-------|
| **Kingdom** | Plantae |
| **Family** | Cannabaceae |
| **Genus** | Cannabis |

&#123;&#123;&lt; /infobox &gt;&#125;&#125;</code></pre>
{{< /details >}}

### imgcard

Displays an image with caption, useful for inline images.

{{< details summary="Variables" >}}
- src
- caption
- width
- float
{{< /details >}}

{{< details summary="Shortcode Example" >}}
<pre><code>&#123;&#123;&lt;imgcard
    title="Cannabis sativa"
    src="https://upload.wikimedia.org/wikipedia/commons/a/a8/Cannabis_leaf.svg"
    caption="A flowering cannabis plant"
    width="20%"
&gt;&#125;&#125;</code></pre>
{{< /details >}}

### details

A collapsible box for hiding content until clicked.

{{< details summary="Variables" >}}
- summary - the clickable text
- open - set to "true" to have it expanded by default
{{< /details >}}

{{< details summary="Shortcode Example" >}}
<pre><code>&#123;&#123;&lt; details summary="Click to expand" &gt;&#125;&#125;
Your hidden content here. Markdown works.
&#123;&#123;&lt; /details &gt;&#125;&#125;</code></pre>
{{< /details >}}

### didyouknow

Displays a random fact from the data file, which changes on each site build.

{{< details summary="Shortcode Example" >}}
<pre><code>&#123;&#123;&lt; didyouknow &gt;&#125;&#125;</code></pre>
{{< /details >}}

{{< details summary="Data File Format" >}}
Add facts to `data/didyouknow.yaml`:
```yaml
- fact: "Your fact here with [links](/articles/page) supported."
- fact: "Another interesting fact."
```
{{< /details >}}

### wikibox

A styled box for homepage sections (Getting Started, Popular Pages, etc.).

{{< details summary="Variables" >}}
- title - the header text
- class - optional custom CSS class
{{< /details >}}

{{< details summary="Shortcode Example" >}}
<pre><code>&#123;&#123;&lt; wikibox title="Getting Started" &gt;&#125;&#125;
Your content here. Markdown works.

- [Link one](/articles/page)
- [Link two](/articles/other)
&#123;&#123;&lt; /wikibox &gt;&#125;&#125;</code></pre>
{{< /details >}}

### link

Creates wiki-style links. Shows as red if the target page doesn't exist.

Note: This shortcode is optional. Standard markdown links like `[title](page-name)` work well for most cases.

{{< details summary="Variables" >}}
- First param: link text (also used as page name if only one param)
- Second param (optional): the actual page path
{{< /details >}}

{{< details summary="Shortcode Example" >}}
<pre><code>&#123;&#123;&lt; link "Cannabis" &gt;&#125;&#125;
Links to /articles/cannabis with text "Cannabis"

&#123;&#123;&lt; link "the sativa plant" "cannabis-sativa" &gt;&#125;&#125;
Links to /articles/cannabis-sativa with text "the sativa plant"</code></pre>
{{< /details >}}

## See Also

- [Contributing](contributing) - How to contribute
- [Style Guide](style) - Writing conventions


---

More on Hugo:

In Hugo's template system:

  - single.html - Used for individual content pages (regular .md files)
  - list.html - Used for section/index pages (_index.md files)

  So list.html is used for:
  - /about/ (from _index.md)
  - /articles/
  - /categories/
  - /categories/cannabinoids/
  - Any taxonomy or section landing page

  And single.html is used for:
  - /about/contributing/ (from contributing.md)
  - /about/editing/
  - /articles/thc/
  - Any regular content page

---