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

I am a postdoctoral researcher working on the impacts of heat and climate change on vulnerable populations, on the effectiveness of local heat adaptation policy, and on its implementation, namely regarding climate shelter networks (see [dedicated tab](/climate-shelters/)), heat action plans (under the EU project [HEATSAFE](https://heatsafe.interreg-euro-med.eu/)) and Nature-based solutions (under the EU project [NBRACER](https://nbracer.eu/)).

Before that, I worked on the design, implementation and evaluation of European public policies — at the Brussels think tank Bruegel, co-authoring studies for the European Commission and the European Parliament on Cohesion Policy and the Just Transition Fund, and at the European Commission's Joint Research Centre, on the European Semester. Earlier I was an economic analyst at the consultancy Oxera, in England. My research has also covered impact evaluation and statistical inference on measures of inequality.

I hold PhDs in Economics from Ca' Foscari University of Venice and in Environmental Sciences from the Autonomous University of Barcelona, completed under a Marie Skłodowska-Curie fellowship. I also hold a Master's degree in Econometrics from Maastricht University and a Bachelor's degree in Economics from Nova SBE in Lisbon.

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
