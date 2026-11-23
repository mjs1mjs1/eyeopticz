---
title: Open questions in the optics of human vision
description: Research by Michael J. Simpson, Ph.D., on parts of human vision that are rarely measured or discussed, including the nodal point of the eye, far peripheral vision and negative dysphotopsia.
hide_byline: true
---

<p class="lead">I spent more than 25 years in industry on the research and development of intraocular lenses, the artificial lenses implanted during cataract surgery. That work led me to questions about human vision that have rarely been studied. This site sets out what I have found, with the papers, simulations and historical sources behind it.</p>

Each topic page starts with a short plain-language summary, followed by the detail and the papers. Corrections and observations are welcome.

<div class="cards">
  <a class="card" href="{{ '/nodal-point/' | relative_url }}"><span>Nodal point</span><strong>How does the eye map very wide angles onto the retina?</strong></a>
  <a class="card" href="{{ '/far-peripheral-vision/' | relative_url }}"><span>Far peripheral vision</span><strong>Why is vision beyond 60 degrees almost never measured?</strong></a>
  <a class="card" href="{{ '/negative-dysphotopsia/' | relative_url }}"><span>Negative dysphotopsia</span><strong>Why do some people see a dark shadow after cataract surgery?</strong></a>
  <a class="card" href="{{ '/history/' | relative_url }}"><span>History of optics</span><strong>Where did the nodal point and "focal length" of the eye come from?</strong></a>
</div>

## Recent papers

{% assign recent = site.data.publications.journal | slice: 0, 4 %}
{% include pub-list.html items=recent %}

Other current topics include the tilt of intraocular lenses relative to the optical axes of the eye, which is linked to the fovea not lying on the optical axis ("angle alpha"), and how eye length and myopia can change.

[All publications]({{ '/publications/' | relative_url }})
