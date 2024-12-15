---
layout: howto
title: How To Articles
---
{% assign sorted_pages = site.pages | sort:"title" %}

<div data-aaad='true' data-aa-adunit='/22247219933/shotcutorg_Desktop_728_1'></div>
<div data-aaad='true' data-aa-adunit='/22247219933/shotcutorg_Mobile_300_1'></div>
<div data-aaad='true' data-aa-adunit='/22247219933/shotcutcom_Desktop_728_1'></div>
<div data-aaad='true' data-aa-adunit='/22247219933/shotcutcom_Mobile_300_1'></div>
<div data-aaad='true' data-aa-adunit='/22247219933/shotcutapp_Desktop_728_1'></div>
<div data-aaad='true' data-aa-adunit='/22247219933/shotcutapp_Mobile_300_1'></div>

- #### [Online Shotcut User Guide](https://forum.shotcut.org/t/table-of-contents/43285)
- #### [PDF Shotcut User Guide (English)](Shotcut%20User%20Guide.pdf)
- #### [Tutorials in the Forum](https://forum.shotcut.org/c/tutorial/5)

{% for page in sorted_pages %}
  {% if page.category == 'help' %}
- #### [{{ page.title }}]({{ site.baseurl }}{{ page.url }})
  {% endif %}
{% endfor %}
