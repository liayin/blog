---
layout: post
title: GitHub Pages Jekyll Blog
date: 2021-02-24 16:06:00 --0000
permalink: /posts/github-pages-jekyll-blog/
---

[Bill Raymond's Tutorial on How to Set Up A Jekyll Blog](https://www.youtube.com/watch?v=EmSrQCDsMv4)

[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

[Grouping posts by topic](https://jekyllrb.com/tutorials/navigation/)

[Add navigation](https://jekyllrb.com/tutorials/navigation/#scenario-9-nested-tree-navigation-with-recursion)

[Add sidebar](https://justus.science/blog/2015/04/17/a-sweetass-sidebar.html)

Of course, in order to change the layout of the page, there needs to be some modifications of the .css file. If we want to display two columns side by side, we could use the CSS Grid like [here](https://www.cssmakeovers.com/patterns/two-columns-infinite/).

The style sheet used by the `minima` theme is called [sass](https://sass-lang.com/), and the file extension is .scss. In scss, the [way](https://rivet.iu.edu/add-ons/rivet-shell/) to add the sidebar is to add it under the `main` element.