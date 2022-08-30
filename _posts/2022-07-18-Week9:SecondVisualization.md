---
layout: post
title: Week 9
---

**Second Visualization**

In the second half of the project we focused less on technical visualization development and more on contextual research

<iframe width="100%" height="346.046875" frameborder="0"
  src="https://observablehq.com/embed/@sommerharris/untitled?cells=chartS"></iframe>


Here is the code for the visualization above:

datawoNullCountry = data.filter((d) => d.country !== null)

data = d3.csv(url, d3.autoType)

chartS = vl
  .markBar()
  .encode(vl.y().fieldN("country"), vl.x().count())
  .data(datawoNullCountry)
  .render({ renderer: "SVG" })
