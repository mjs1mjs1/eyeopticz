---
title: "The nodal point of the eye: how the retinal image scales to wide angles"
description: The nodal point is usually defined only for small angles, yet it describes the retinal image of the eye out to very wide angles. Why this works, what effective focal length means for the eye, and the historical sources.
topic_key: nodal
updated: 2026-11-23
---

<p class="lead">The nodal point is normally defined for small angles and flat surfaces. Yet for the human eye it can be used to scale the image on the retina out to very large angles. This works because the cornea and the retina are both curved, and their effects largely cancel.</p>

## In brief

- The **nodal point** is a reference point in an optical system. A ray aimed at the first nodal point leaves from the second at the same angle.
- In textbook optics this only holds for rays close to the axis (the "paraxial" region).
- In the eye, light from very wide angles still lands on the retina roughly where the nodal point predicts. Many people assumed this, but it had not been explained in print.
- The explanation is the **curvature of the cornea and the retina**. The cornea bends incoming rays so that angles at the exit pupil are about 0.8 times the input angles. The retina then curves round to meet the image.
- Seen from the nodal point, which sits close to the back surface of the crystalline lens, the angle to a point on the retina is roughly the same as the angle of the light coming in.

<figure class="diagram">
<svg viewBox="0 0 380 260" role="img" aria-label="Schematic of the eye showing a wide-angle ray entering the cornea at angle theta, travelling inside the eye at about 0.8 theta, and reaching a point on the curved retina that lies at roughly theta from the nodal point N">
  <path d="M177 27 A105 105 0 1 1 177 233" fill="none" stroke="currentColor" stroke-opacity=".45" stroke-width="2"/>
  <path d="M128 45 L177 27 M128 215 L177 233" fill="none" stroke="currentColor" stroke-opacity=".45" stroke-width="2"/>
  <path d="M128 45 Q52 130 128 215" fill="none" stroke="currentColor" stroke-width="2"/>
  <ellipse cx="185" cy="130" rx="22" ry="45" fill="none" stroke="currentColor" stroke-opacity=".6" stroke-width="1.5"/>
  <line x1="20" y1="130" x2="330" y2="130" stroke="currentColor" stroke-opacity=".3" stroke-dasharray="4 4"/>
  <line x1="71" y1="21" x2="111" y2="66" stroke="var(--accent)" stroke-width="2"/>
  <line x1="111" y1="66" x2="276" y2="197" stroke="var(--accent)" stroke-width="2"/>
  <line x1="215" y1="130" x2="276" y2="197" stroke="currentColor" stroke-opacity=".7" stroke-dasharray="3 3"/>
  <circle cx="215" cy="130" r="3.5" fill="currentColor"/>
  <circle cx="276" cy="197" r="3.5" fill="var(--accent)"/>
  <text x="221" y="122">N</text>
  <text x="56" y="56">θ</text>
  <text x="138" y="76">≈ 0.8 θ</text>
  <text x="262" y="226">≈ θ seen from N</text>
  <text x="292" y="50">retina</text>
  <text x="24" y="200">cornea</text>
  <text x="160" y="190">lens</text>
</svg>
<figcaption>Schematic only, not to scale. A wide-angle ray is bent at the cornea, travels inside the eye at about 0.8 of its original angle, and reaches the curved retina at a point that, seen from the nodal point N, lies at roughly the original angle.</figcaption>
</figure>

## Why it matters

Most models of the eye, and most measurements of vision, concentrate on the central few degrees. Knowing that the nodal point still describes where light lands at very wide angles gives a simple way to relate angles in the world to positions on the retina across the whole visual field. That matters for understanding [far peripheral vision]({{ '/far-peripheral-vision/' | relative_url }}) and the shadow of [negative dysphotopsia]({{ '/negative-dysphotopsia/' | relative_url }}) after cataract surgery.

## What "effective focal length" means for the eye

The term **effective focal length** (EFL) is used loosely. Historically the term was "equivalent focal length". For a lens in a fluid such as the eye, the EFL is the focal length divided by the refractive index, as given in Warren Smith's *Modern Optical Engineering* (1966). For the eye, this places the nodal point at f′/n′ from the retina.

An open question: I have not found a clear historical source for when and why the modern definition of EFL was adopted. If you know one, please get in touch.

## Papers on this topic

{% include related-papers.html topic="nodal" %}

## Related

- [Historical sources on the nodal point and paraxial optics]({{ '/history/' | relative_url }}), from Gauss (1841) and Listing (1845) onwards
- [English translation of Listing (1845)]({{ '/papers/listing-1845-translation/' | relative_url }}), where the nodal point of the eye was introduced
- [Far peripheral vision]({{ '/far-peripheral-vision/' | relative_url }})
