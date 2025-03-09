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
个人水平有限，博客很多内容借鉴了前人的智慧，**涉及版权问题**请及时联系作者下架处理。  
怀着记录学习的心态，建设了这个博客站，大家对本站有什么想法欢迎各位联系作者，一起打造更好的内容！  

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
