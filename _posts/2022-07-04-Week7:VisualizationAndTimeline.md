---
layout: post
title: Week 7
---

**Timeline Visualization Creation**

One of the user scenarios we generated for our research question was for a hypothetical phd student who wants to be able to sort the data by date and see the ai
instances organized into a timeline. This user wants to be able to see and compare the date of the instance and the date the public found out about the instance on the same graph. For some of these, they will be the same, as when a user notices the problem immediately when they use the tool, and this knowledge quickly spreads through the general public. Sometimes there will be more of a gap between the two dates. For example, when users' data is being collected and used for nefarious purposes, people may not realize this is happening until much damage has been caused.

A more specific user scenario we came up with was that the phd student wanted to be able to sort by periods of time so that she could see any trends for when certain political parties were in power, versus others. While we don't know whether there would be any significant trends in this scenario, articulating the user's desire helps us to build specific, completable features in our data visualization.

Here, I am embedding an entire notebook with various experiments, some moderately successful, and some unsuccessful. I hope this gives you a window into what my work looked like as I was learning to use observable. In the text after the following embedding, I will break down some of what I learned in these experiments. I find looking at these flawed examples will provide more insight to my data than just breaking down a polished example.

<iframe width="100%" height="500" frameborder="0"
  src="https://observablehq.com/embed/2ed9bcdeef401cb3?cell=*"></iframe>

The first four items (the drop down selections) allow the user to choose what to display in the following visualization. The visualization below the drop down menus is our first attempt at a timeline. We simply created an X Y plot, then collapsed the Y axis. If you play around with the drop down values, you will see that some of them don't quite make sense on this visualization, and some of them flat out do not work. This is where we would want to limit options to only those that make sense on the visualization. For example, it doesn't make sense to change the Y value because it has been collapsed, and it only makes sense to set the X value to 'date of occurrence' or 'date the public found out', since this is a timeline we are building.

The next two plots (with no data displayed on them) were further attempts to explore different ways of visulizing the data. I never got the data to correctly show up on these plots, as I believe the data and graph scopes were not aligned. The experimentation process involved a lot of these kinds of results. I eventually abandoned these visualizations, as well as the timeline attempt above, because I was building them using the 'plot' library in observable, which does not allow as much flexibility as d3 and vegalite. 

The navio (the next tool), is a data selection visualization tool that our advisor, John, created. You can use the navio to sort the data by simply going to the column that one wants to sort, then selecting the portion of data that you want to look at. Try looking at the source column (click to select), then select the 'awful-ai' data. You can hover the mouse to see the data label and can click and drag to select a portion of the data. Scroll back up and notice how selecting through novio changes what data is available for display in the graphs above.

Below the navio, you can see our data displayed, first as an array of objects, and then in an organized table. 

Below the data, you can see a histogram made with vegalite and a messy attempt at a histogram using d3. The bottom histogram (in d3) was abandoned in favor of the approach we used on the top one (vegalite).

Below that you can see a sliding scale to generate a certain number of buttons, using information from the data. While this was not integrated into a larger visualization, it gave us a sense of how one could give the user a way to select certain categories of instance, even with unknown incoming data.

In summary, I would say the most valuable takeaways from the particular visualizations on this page are that ultimately the plot library didn't give us the control and flexibility we wanted, and to look to visualizations like navio to get inspiration for state of the art practices in data visualization.
