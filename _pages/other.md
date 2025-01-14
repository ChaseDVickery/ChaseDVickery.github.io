---
layout: archive
title: "Other Projects"
permalink: /other/
author_profile: true
---

{% include base_path %}

### Other Projects
{% for post in site.other reversed %}
  {% include archive-single.html %}
{% endfor %}
