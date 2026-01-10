---
layout: default
title: Blog
---
<div class="align-center" markdown="block">
## git co -b idk-what-im-doing

__a friendly little tech blog for learners of all levels__

I love tackling fundamental web development topics in an accessible & engaging manner.
</div>

{% for post in site.posts %}
  {% capture words %}{{ post.content | number_of_words }}{% endcapture %}
  {% capture minutes %}{{ words | divided_by: 275 }}{% endcapture %}

  <div class="content__section">
    <div class="content__section__media">
      <a href="{{ post.url }}">
        <img class="content__section__image" src="{{ post.image }}" alt="{{ post.image_alt }}">
        </a>
    </div>

    <div class="content__section__text" markdown="block">
## [{{ post.title }}]({{ post.url }})
#### {{ post.description }}
__{{ post.date | date: '%B %d, %Y'  }}__
_&#8226; {{ words }} words &#8226; {{ minutes }} minute read_

{{ post.excerpt }}
_[read more...]({{ post.url }})_
</div>
  </div>
{% endfor %}
