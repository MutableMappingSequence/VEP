---
layout: default
title: VEP 列表
permalink: /veps/
---

# VEP 列表

{% assign sorted = site.veps | sort: 'vep' %}

| VEP | 标题 | 状态 | 类型 |
|-----|------|------|------|
{% for vep in sorted %}
| [VEP {{ vep.vep }}]({{ vep.url | relative_url }}) | {{ vep.title }} | {{ vep.status }} | {{ vep.type }} |
{% endfor %}
