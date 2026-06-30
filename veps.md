---
layout: default
title: VEP 列表
permalink: /veps/
---

# VEP 列表

{% assign sorted = site.veps | sort: 'vep' %}

<table>
  <thead>
    <tr><th>VEP</th><th>标题</th><th>状态</th><th>类型</th></tr>
  </thead>
  <tbody>
{% for vep in sorted %}
    <tr>
      <td><a href="{{ vep.url | relative_url }}">VEP {{ vep.vep }}</a></td>
      <td>{{ vep.title }}</td>
      <td>{{ vep.status }}</td>
      <td>{{ vep.type }}</td>
    </tr>
{% endfor %}
  </tbody>
</table>
