---
title: About
description: About this page
draft: false
date: 2026-01-11
categories:
  - About
related:
  - Cannabis Sativa
  - Cannabis Indica
  - Cannabis Ruderalis
---


## About the Wiki Style

To be a good wiki, pages should be 
- editable by the people
- navigate fluidly between links





## Contributing

On each page, you will see an "Edit" link near the top right. 
If you click on the link, it will take you to a Github page where changes can be made to the page. 

Since the contents of this page are stored and hosted on Github, you must have an account with Github to make changes to the content. 
When changes are made, they are made in a branch called `Edit`. Submit a pull request merging your changes to `Edit` into `Main`.


## Hugo

This site is created using Hugo. 

When writing on pages, there are certain Hugo "Shortcodes" that can be used to inject html.

## Article Frontmatter

## Shortcodes

### imgcard

Variables:
- src
- caption
- width

Example: 
```
{{</* imgcard src="images/gnome.jpg" caption="Welcome" width="20%" */>}}
```

<hr style="color:green; opacity;.1;border-style:dashed;">

### infobox

Variables: 
- title
- image
- caption

And add the table/content sandwiched inbetween.

```
{{</* infobox
    title="Cannabis sativa"
    image="https://upload.wikimedia.org/wikipedia/commons/a/a8/Cannabis_leaf.svg"
    caption="A flowering cannabis plant"
>}}

| Field | Value |
|-------|-------|
| **Kingdom** | Plantae |
| **Clade** | Tracheophytes |
| **Order** | Rosales |
| **Family** | Cannabaceae |
| **Genus** | Cannabis |
| **Species** | C. sativa |

{{< /infobox */>}}
```

### link



## Other Design Nuances

- Use `##` or `<h2>` for headers that have an underline to help layout the page.

