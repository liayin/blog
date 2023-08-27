---
layout: post
title: Web scraping
date: 2022-8-25 10:00:01 --0000
permalink: /posts/web-scraping/
---

(Updated 8-8-2023)

* TOC
{:toc}

## Links
[Harvard tutorial](https://iqss.github.io/dss-webscrape/index.html)

[William Marble](https://williammarble.co/files/webscraping_tutorial/webscraping_tutorial.pdf)

[Stanford](https://sites.google.com/a/stanford.edu/rcpedia/screen-scraping/web-scraping-with-r)

[MIT](https://vialab.mit.edu/tutorials/module/scraping-websites/)

## Python

### xpath
xpath with multiple layers:
```Python
driver.find_elements("xpath", "//pre[contains(@class, 'ma-0')]|//span[contains(@class, 'font-weight-bold')]")
```

xpath with and statement:
```Python
hidden_price_elements = driver.find_elements("xpath", "//*[contains(@class, 'click-to-see') and (contains(@class, 'category-slider__item__price category-slider__item__price--inline'))]")
driver.find_elements(By.XPATH, "//button[contains(@aria-label, 'Next page') and not(contains(@class, 'disabled'))]")
```

xpath with or statement:
```Python
driver.find_elements("xpath", "//button[contains(@class, 'class name')]//span[contains(@class, 'subclass name')] | //button[contains(@class, 'class name 2')]//span[contains(@class, 'subclass name')]")
```