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
social: true # includes social icons at the bottom of the page

announcements:
  enabled: false # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

I am a postdoctoral researcher at the [CMCC](https://www.cmcc.it/people/midoes-catarina) working on the impacts of heat and climate change on vulnerable populations, on the effectiveness of local heat adaptation policy, and on its implementation, namely regarding climate shelter networks (see [dedicated tab](/climate-shelters/)), heat action plans (under the EU project [HEATSAFE](https://heatsafe.interreg-euro-med.eu/)) and Nature-based Solutions (under the EU project [NBRACER](https://nbracer.eu/)).

Before, I worked on the design, implementation and evaluation of European public policies, both at the Brussels think tank Bruegel and in the European Commission's Joint Research Centre.

I hold PhDs in Economics and in Environmental Science completed under a Marie Skłodowska-Curie fellowship, and a Master's in Econometrics.

<div class="shuffled-interests" markdown="1">

#### Research interests (in randomized order):

- Inference
- Inequality
- Heat Adaptation Policy
- Climate Change Policy
- Impact Evaluation

</div>

<div class="shuffled-interests" markdown="1">

#### Non-exclusively-research interests (in randomized order):

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
