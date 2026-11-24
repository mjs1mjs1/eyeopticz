---
layout: home
title: Open questions in the optics of human vision
lead: I spent more than 25 years in industry on the research and development of intraocular lenses, the artificial lenses implanted during cataract surgery. That work led me to questions about human vision that have rarely been studied. This site sets out what I have found, with the papers, simulations and historical sources behind it.
description: Research by Michael J. Simpson, Ph.D., on parts of human vision that are rarely measured or discussed, including the nodal point of the eye, far peripheral vision and negative dysphotopsia.
---

<div class="cards">
  <a class="card c-teal" href="{{ '/nodal-point/' | relative_url }}">{% include icon.html name="nodal" %}<span>Nodal point</span><strong>How does the eye map very wide angles onto the retina?</strong></a>
  <a class="card c-amber" href="{{ '/far-peripheral-vision/' | relative_url }}">{% include icon.html name="peripheral" %}<span>Far peripheral vision</span><strong>Why is vision beyond 60 degrees almost never measured?</strong></a>
  <a class="card c-coral" href="{{ '/negative-dysphotopsia/' | relative_url }}">{% include icon.html name="dysphotopsia" %}<span>Negative dysphotopsia</span><strong>Why do some people see a dark shadow after cataract surgery?</strong></a>
  <a class="card c-indigo" href="{{ '/history/' | relative_url }}">{% include icon.html name="history" %}<span>History of optics</span><strong>Where did the nodal point and "focal length" of the eye come from?</strong></a>
</div>

<div class="prose" markdown="1">

{% if site.author.photo != "" %}
<figure class="portrait"><img src="{{ '/assets/img/' | append: site.author.photo | relative_url }}" alt="{{ site.author.display }}"></figure>
{% endif %}

Each topic page starts with a short plain-language summary, followed by the detail and the papers. Corrections and observations are welcome.

## Recent papers

{% assign recent = site.data.publications.journal | slice: 0, 4 %}
{% include pub-list.html items=recent %}

Other current topics include the tilt of intraocular lenses relative to the optical axes of the eye, which is linked to the fovea not lying on the optical axis ("angle alpha"), and how eye length and myopia can change.

[All publications]({{ '/publications/' | relative_url }})

</div>
