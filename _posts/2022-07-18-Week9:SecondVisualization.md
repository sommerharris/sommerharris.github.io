---
layout: post
title: Week 9
---

**Second Visualization**

In the second half of the project we focused less on technical visualization development and more on contextual research. We still did a little bit of visualization creating as we finished up the Summer. The following visualization was created in d3 rather that the plot library. It displays the country and the number of unethical ai records from that country. Granted, this is a reflection of the distribution of our dataset, rather than the world at large. I would want to know much more about the process of data collection and the existence of AI before being able to claim that this distribution is an accurate representation of the world.

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
  
In the first line we filter out any of the records for which the 'country' column is null. 

Next, we convert the data so that it will work with our d3 library. 

Lastly, we can use markBar and encode to create the graph, put the data in with the data function, and then render it to an SVG.

While this visualization is not our ending point, it is a clean example of us using d3 with this dataset. If we had more time on this project, after we developed our proposed features in the technical paper, we would then return to building these features using d3 and vegalite.
