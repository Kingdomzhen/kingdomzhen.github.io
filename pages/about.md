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
作者目前是某在读研究生身份，个人水平有限，精力也有限，此博客所以资料都是在网上整理总结出来的，可以说**毫无原创可言**，观点也并非十分不准确，有重复造轮子的嫌疑，博客中甚至夹杂着错别字。抱着边学边卖的心态我开通了这个博客，非常欢迎大家一起留言探讨技术，或是给我发email共同完善构建这个知识库。

以下是我的技术栈，我将适当整理，逐步开源
如有侵权，请联系作者删帖  
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
