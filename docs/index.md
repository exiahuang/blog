---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
---

<div class="bs-docs-featurette">
  <div class="container">
        {% for post in site.posts %}	
            <h3><a href="{{ post.url | prepend:site.baseurl }}">{{ post.title }}</a></h3>
            <p><small><strong>{{ post.date | date: "%B %e, %Y" }}</strong> . {{ post.category }} . </small></p>			
        {% endfor %}	
  </div>
</div>
