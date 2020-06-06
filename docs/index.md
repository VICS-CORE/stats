---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
title: Home
list_title: Recent

---
<dl>
  {% for post in site.posts %}
    <dt>
        <h4 style="margin:0;"><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h4>
        <h6>{{ post.date | date: "%b %d, %Y" }}</h6>
    </dt>
    <dd>
        <p>{{ post.excerpt }}</p>
    </dd>
  {% endfor %}
</dl>
