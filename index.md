---
---

<img alt="Photo of me" src="./img/photo.jpg" style="float: right; max-width: max(15vw,20vh); margin-left: 1vw;" />

[CV](./pdf/cv.pdf) |
[GitHub](https://github.com/{{ site.me.github }}) |
[LinkedIn](https://linkedin.com/in/{{ site.me.linkedin }})

{{ site.me.summary }}

---

{% for post in site.posts %}
## [{{ post.title }}]({{ post.url }})
{{ post.excerpt }}
{% endfor %}
