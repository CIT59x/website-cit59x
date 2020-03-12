---
title: "tooltip test"
date: 2020-02-19T12:52:36+06:00
image_webp: images/blog/blog-post-3.webp
image: images/blog/blog-post-3.jpg
author: Logan Ayliffe
description : "tooltip test"
---

{{< tooltip >}}This is an example of the tooltip shortcode.{{< definition >}}Hi there, @phildini.{{< /definition >}}{{< /tooltip >}}



Here's what I did:


In a file called tooltip.html in my shortcodes directory:

```

<style>
    .definition {
        visibility: hidden;
        width: 120px;
        background-color: #555;
        color: #fff;
        text-align: center;
        border-radius: 6px;
        padding: 5px 0;
        position: absolute;
        z-index: 1;
        bottom: 125%;
        left: 50%;
        margin-left: -60px;
        opacity: 0;
        transition: opacity 0.3s;
    }
    
    .term {
        position: relative;
        display: inline-block;
        border-bottom: 1px dotted black;}
    
    .term:hover .definition {
        visibility: visible;
        opacity: 1;
    }
    </style>
    <span class="term">
     {{ .Inner }} 
    </span>

```


A separate file called definition.html:



```


<span class="definition">{{ .Inner }}</span>

```


[Syntax for use (and directions generally) from this post.](https://discourse.gohugo.io/t/css-in-shortcodes-is-it-working-as-intended-in-0-55/19742/4)

