---
layout: page
title: Technical Notes
---
{% assign sorted_pages = site.pages | sort:"title" %}

<script>
    if (location.hostname.endsWith("shotcut.org")) {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutorg_Desktop_728_1"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutorg_Mobile_300_1"></div>');
    } else if (location.hostname.endsWith("shotcut.com")) {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutcom_Desktop_728_1"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutcom_Mobile_300_1"></div>');
    } else {
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutapp_Desktop_728_1"></div>');
        document.write('<div data-aaad="true" data-aa-adunit="/22247219933/shotcutapp_Mobile_300_1"></div>');
    }
</script>

{% for page in sorted_pages %}
  {% if page.category == 'notes' %}
- #### [{{ page.title }}]({{ site.baseurl }}{{ page.url }})
  {% endif %}
{% endfor %}
