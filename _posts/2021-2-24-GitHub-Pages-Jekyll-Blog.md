---
layout: post
title: GitHub Pages Jekyll Blog
date: 2021-02-24 16:06:00 --0000
permalink: /posts/github-pages-jekyll-blog/
---

This blog post contains information about how I decided to blog, why I chose to use Github Pages Jekyll Blog, which design choices I went with, etc. Hope it is helpful to you.

I have always been publishing on the internet here and there. Sometimes to exhibit information about me, and sometimes to post my thoughts. The current blog was started when I wanted to record information that is useful to my research, and hoped that it would help others who may benefit from this information as well. Also, the webpage is a wonderful way to organize information that I deem superior to writing things down in Word documents or LaTeX documents. 

As I pondered over which blogging service to use, two things were important in my consideration: whether there would be code highlighting and whether I could include equations.

Markdown naturally supports code highlighting for many different languages. Displaying mathematical equations is trickier, but there are many solutions. To start with markdown, [Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) is a great resource.

I started the blog by forking [Barry Clark's Jekyll Now](https://github.com/barryclark/jekyll-now) repository, and writing directly in the repo. 

This year, I came across [Bill Raymond's Tutorial on How to Set Up A Jekyll Blog](https://www.youtube.com/watch?v=EmSrQCDsMv4), and started using VSCode for editing. This is when I changed the original template to the minima theme, which is much simpler. I also manually added a sidebar, which was not included in the original posting. To add the sidebar, I used the following resources:

- [Grouping posts by topic](https://jekyllrb.com/tutorials/navigation/)

- [Add navigation](https://jekyllrb.com/tutorials/navigation/#scenario-9-nested-tree-navigation-with-recursion)

- [Add sidebar](https://justus.science/blog/2015/04/17/a-sweetass-sidebar.html)

If the stylesheets are in the format .css, there needs to be some modifications of the .css file. If we want to display two columns side by side, we could use the CSS Grid like [here](https://www.cssmakeovers.com/patterns/two-columns-infinite/).

The style sheet used by the `minima` theme is called [sass](https://sass-lang.com/), and the file extension is .scss. In scss, the [way](https://rivet.iu.edu/add-ons/rivet-shell/) to add the sidebar is to add it under the `main` element.

There are some other changes to the blog that I would like to implement, such as adding comment boxes to the bottom of the postings, and changing the theme to be a dark theme. Please look forward to the changes.

# LaTeX
[Reference](https://hw311.me/en/jekyll/2019/01/23/support-latex-in-jekyll-blog/)

# DataTables
[Reference](https://idratherbewriting.com/documentation-theme-jekyll/mydoc_tables.html) \
[Example](https://datatables.net/forums/discussion/73237/datatable-on-just-the-docs-github-page) \
DataTables is a plug-in for the jQuery Javascript library. It adds advanced features to HTML tables. The way to include it into Jekyll blogs is to include the following lines into the default layout. In my case, the default head is included in the head.html file in the folder _includes. 

<!-- {% raw %} -->
```html
<head>
    <!--The lines below help include JQuery DataTables into Markdown files-->
    {%- if page.datatable == true -%}
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>  <!--Add JQuery-->
    <link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.12.1/css/jquery.dataTables.css"> <!--add style sheet-->
    <script type="text/javascript" charset="utf8" src="https://cdn.datatables.net/1.12.1/js/jquery.dataTables.js"></script> <!--add dataTables-->
    <script>
        $(document).ready( function () {
        $('table.datatable').DataTable();
        } );
    </script>
    {% endif %}
</head>
```
<!-- {% endraw %}) -->

The last step is to include `datatable: true` in a page's frontmatter. The third step is to add `{: .datatable }` below the tables.