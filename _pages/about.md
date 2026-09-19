---
layout: about
title: about
permalink: /
subtitle:

profile:
  align: right
  image:
  image_circular: false # crops the image to make it circular
  more_info:

selected_papers: false # includes a list of papers marked as "selected={true}"
social: false # includes social icons at the bottom of the page

announcements:
  enabled: false # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

## Research interests

Coming soon.

## Non-predominantly-research interests

<div id="shuffled-interests" markdown="1">

Coming soon.

</div>

<script>
  // Shuffle the list above on every page view, so no interest is permanently
  // first. Fisher-Yates; appending an existing node moves it, so the loop
  // reorders in place. No-ops until the div actually contains a list.
  (() => {
    const list = document.querySelector("#shuffled-interests ul");
    if (!list) return;
    const items = [...list.children];
    for (let i = items.length - 1; i > 0; i--) {
      const j = Math.floor(Math.random() * (i + 1));
      [items[i], items[j]] = [items[j], items[i]];
    }
    list.append(...items);
  })();
</script>
