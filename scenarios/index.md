---
layout: default
---

# Scenarios

{% for file in site.static_files %}
{% if file.path contains "/scenarios/" %}
{% assign robot = file.basename | split: "." %}
{% if current_robot != robot[0] %}

## {{ robot[0] }}

{% endif %}

{% if file.extname == ".svg" %}

![{{ robot[0] }}]({{ file.path }})

{% else %}

- [{{file.name}}]({{ file.path }})

{% endif %}


{% assign current_robot = robot[0] %}
{% endif %}
{% endfor %}
