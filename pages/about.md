---
layout: page
title: About
description: about页面
keywords: ICCI, 博客
comments: true
menu: 关于
permalink: /about/
---
## 作者声明

***联系作者：***  kingdomzhen1@gmail.com

## Skill Keywords

{% for skill in site.data.skills %}
### {{ skill.name }}
<div class="btn-inline">
{% for keyword in skill.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
