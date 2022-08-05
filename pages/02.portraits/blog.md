---
title: Portraits
blog_url: blog
menu: Portraits
body_classes: blog group-blog infinite-scroll

sitemap:
    changefreq: monthly
    priority: 1.03

content:
    items: @self.children
    order:
        by: date
        dir: desc
    limit: 12
    pagination: true

feed:
    description: Sample Blog Description
    limit: 12

pagination: true
---
