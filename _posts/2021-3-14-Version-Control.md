---
layout: post
title: Version Control
date: 2021-03-14 20:31:00 --0000
permalink: /posts/version-control/
---
<ul>
   {% for item in site.data.nav.nav %}
      <li><a href="{{ item.url }}">{{ item.title }}</a></li>
   {% endfor %}
</ul>


Version control is very useful for working with R projects, as well as other analytics/software projects, because if you have deleted some content from the code file, and later would like to restore it, version control gives you the option to do so.

## RStudio

Garrett Grolemund's [tutorial](https://rstudio.com/resources/webinars/managing-part-2-github-and-rstudio/) on the RStudio website is a good starting point for learning version control in RStudio. 

The role that RStudio plays in version control, is that it has a built-in interface with Git, so commiting changes and keeping track of previous versions of the project can be done in R. However, in order to see a previous version of a file in your R project, you still need to use the command line (or a Git GUI) to do it.

Nevertheless, the simplicity of committing changes directly from RStudio makes it a good idea to add version control to your project.

## Jupyter Notebook

For Jupyter Notebook, a good way to perform version control is with a JupyterLab extension called [jupyterlab-git](https://github.com/jupyterlab/jupyterlab-git). The advantage of this tool over many others is that it is able to integrate with GitHub, as well as version control locally. After it has been configured correctly, make sure to open Jupyter Notebook through Jupyterlab with the `jupyter lab` command.