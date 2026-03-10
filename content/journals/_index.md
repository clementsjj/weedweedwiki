---
title: Grow Journals
description: Community grow journals documenting plant journeys
draft: false
layout: single
date: 2026-02-04
---

**Grow Journals** are community-submitted pages documenting the journey of growing plants - cannabis, tomatoes, herbs, flowers, or anything else. Share your progress, photos, successes, and lessons learned.

## Start Your Own Journal

Ready to document your grow? Enter a name for your journal:

<div class="journal-starter" style="display: flex; gap: 0.5rem; margin: 1rem 0; flex-wrap: wrap;">
  <input type="text" id="journal-name" placeholder="e.g. Balcony Tomatoes 2026" style="padding: 0.5rem; font-size: 1rem; border: 1px solid #a2a9b1; flex: 1; min-width: 200px;" />
  <button id="start-journal-btn" class="start-journal-button" style="padding: 0.5rem 1rem; font-size: 1rem; background: #36c; color: white; border: none; cursor: pointer;">Start a Journal →</button>
</div>

<script>
document.getElementById('start-journal-btn').addEventListener('click', function() {
  const input = document.getElementById('journal-name').value.trim();
  if (!input) {
    alert('Please enter a name for your journal');
    return;
  }
  // Convert to URL-friendly slug
  const slug = input.toLowerCase()
    .replace(/[^a-z0-9\s-]/g, '')
    .replace(/\s+/g, '-')
    .replace(/-+/g, '-');

  const title = encodeURIComponent(input);
  const today = new Date().toISOString().split('T')[0];

  const template = `---
title: ${input}
author: your-username
date: ${today}
plant:
---

Write about your grow here!

## The Setup

Describe what you're growing and your setup.

## Progress

Add dated updates as your grow progresses.

## Week 1

Your update here...

![photo description](your-photo.jpg)
`;

  const encoded = encodeURIComponent(template);
  const url = `https://github.com/clementsjj/weedweedwiki/new/main/content/journals?filename=${slug}/index.md&value=${encoded}`;
  window.open(url, '_blank');
});

// Allow Enter key to submit
document.getElementById('journal-name').addEventListener('keypress', function(e) {
  if (e.key === 'Enter') document.getElementById('start-journal-btn').click();
});
</script>

You'll need a GitHub account. After clicking:

1. Rename `my-journal-name` to something descriptive (use dashes, like `balcony-tomatoes-2026`)
2. Fill in your details and write your journal
3. Submit a pull request

## Adding Photos

Each journal is a folder, so you can upload images right alongside your journal:

```
journals/
  my-journal-name/
    index.md        ← your journal
    seedling.jpg    ← your photos
    harvest.jpg
```

Then reference images simply:
```markdown
![My seedling](seedling.jpg)
```

Or, you can link to image files from other sites like so: 
```markdown
![Image File](https://i.imgur.com/RKpt0g3.jpeg)
```

Or, you can drag and drop into the markdown editor. 
You will see a link in an `<img>` tag. That is github saving the photo to their own CDN. 
This is a good option as well.

## Tips

- **Dates** - Include dates with updates so readers can follow the timeline
- **Be yourself** - No strict format, write however works for you
- **Link to articles** - Reference wiki pages like [pests](../articles/pests) or [strain](../articles/strains) info
    - You will need to go "back" to articles, like this: `[pests](../articles/pests)`
- **Update as you go** - Edit your journal to add new progress

## Community Journals

{{< childpages >}}