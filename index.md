---
layout: portfolio
---

<style type="text/css">
    .section {
        border-width: 1px;
        border-color: #e0e0e0;
        border-style: solid;
        border-radius: 7px;
        padding: 10px;
        margin: 5px;
    }

    .section-container {
        display: flex;
    }

    .heading {
        padding: 10px;
        display: flex;
    }

    .heading-section {
        padding: 10px;
    }

    .section-title {
        font-size: 14pt;
        font-weight: bold;
        padding-left: 5px;
    }
</style>

<div class="heading">
    <div class="heading-section">
        <img src="ihab-awad.png" width="600px">
    </div>

    <div class="heading-section">
        <p>My name is Ihab Awad. Welcome to my online portfolio!</p>

        <p>I am an engineer, visionary, and maker. I build things for a living and for fun, and lead teams with enthusiasm and a growth mentality for myself and for others. I learn what I need to – usually but not always in engineering – to accomplish my goals. I seek interesting problems, and a place where my leadership style is appreciated and can thrive.</p>

        <p>I hope the material here can give you an idea of what I'm about and what excites me.</p>
    </div>
</div>

{% for section in site.data.list %}
  <div class="section">
    <div class="section-title">{{ section.title }}</div>
    <div class="section-container">
      {% for entry in section.entries %}
        {% include card.md %}
      {% endfor %}
    </div>
  </div>
{% endfor %}

<div>
Content credits:
<ul>
<li><a href="https://pixabay.com/users/hai443-39753619/">Hai443</a></li>
<li><a href="https://www.flaticon.com/free-icons/pinky-promise" title="pinky promise icons">Pinky promise icons created by Freepik - Flaticon</a></li>
</ul>
</div>

