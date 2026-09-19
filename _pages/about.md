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

#### Research interests (in randomized order)

<div class="shuffled-interests" markdown="1">

- Inference
- Inequality
- Heat Adaptation Policy
- Climate Change Policy
- Impact Evaluation

</div>

#### Non-exclusively-research interests (in randomized order)

<div class="shuffled-interests" markdown="1">

- Rights of prisoners
- Political discourse
- Political theory
- Gender norms
- Violence propagation

</div>

<script>
  // Shuffle every .shuffled-interests list on each page view, so no interest is
  // permanently first. Fisher-Yates; appending an existing node moves it, so the
  // loop reorders in place. A div with no list in it is simply skipped.
  document.querySelectorAll(".shuffled-interests ul").forEach((list) => {
    const items = [...list.children];
    for (let i = items.length - 1; i > 0; i--) {
      const j = Math.floor(Math.random() * (i + 1));
      [items[i], items[j]] = [items[j], items[i]];
    }
    list.append(...items);
  });
</script>
