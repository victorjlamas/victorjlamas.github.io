### Publications

This is a list of all my publications in chronological and alphabetical order. For a more thematic ordering and some context, see the research site.

{% assign pubCounter = 1 %}
<details>
<summary style="cursor:pointer;"><b style="cursor:pointer;">Dissertation</b></summary>

<ol start="{{ pubCounter }}">
{% assign pubCounter = pubCounter | plus:1 %}
<li> Victor Lamas. <a href="assets/papers/diss.pdf" target="_blank" rel="me noopener noreferrer"><b>TODO</b></a> TODO <a href="assets/papers/diss.pdf" target="_blank" rel="me noopener noreferrer"><img src="logos/pdf.png" height="12px" style="margin-inline-start: 0.75em" alt="pdf"/></a></li>
</ol>
</details>


<details>
<summary style="cursor:pointer;"><b style="cursor:pointer;">Journal Articles</b></summary>

{% assign prev_year = "" %}
{% for pub in site.data.bib.journals %}
{% capture this_year %}{{ pub.year }}{% endcapture %}
{% if prev_year != this_year %}
{% if prev_year != "" %}
</ol>
{% endif %}
{% assign prev_year = this_year %}
<b>{{ this_year }}</b>
<ol start="{{ pubCounter }}">
{% endif %}
  
<li style="margin: 5px;">{{ pub.author }}: {% if pub.id != "" %}<a href="assets/papers/{{ pub.id }}.pdf" target="_blank" rel="me noopener noreferrer">{% endif %}<b>{{ pub.title }}</b>{% if pub.id != "" %}</a>{% endif %} {{ pub.journal }}, {{ pub.pages }}, {{ pub.year }}. doi: {{ pub.doi }} {% if pub.id != "" %}<a href="assets/papers/{{ pub.id }}.pdf" target="_blank" rel="me noopener noreferrer"><img src="logos/pdf.png" height="12px" style="margin-inline-start: 0.75em" alt="pdf"/></a>{% endif %}</li>
{% assign pubCounter = pubCounter | plus:1 %}
{% endfor %}
</ol>
</details>


<details>
<summary style="cursor:pointer;"><b style="cursor:pointer;">Conference & Workshop Papers</b></summary>

{% assign prev_year = "" %}
{% for pub in site.data.bib.proceedings %}
{% capture this_year %}{{ pub.year }}{% endcapture %}
{% if prev_year != this_year %}
{% if prev_year != "" %}
</ol>
{% endif %}
{% assign prev_year = this_year %}
<b>{{ this_year }}</b>
<ol start="{{ pubCounter }}">
{% endif %}
  
<li style="margin: 5px;">{{ pub.author }}: {% if pub.id != "" %}<a href="assets/papers/{{ pub.id }}.pdf" target="_blank" rel="me noopener noreferrer">{% endif %}<b>{{ pub.title }}</b>{% if pub.id != "" %}</a>{% endif %} {{ pub.booktitle }}, {{ pub.publisher }}, {{ pub.year }}. {% if pub.doi != "" %} doi: {{ pub.doi }} {% elsif pagpube.link != "" %} link: {{ pub.link }} {% endif %} {% if pub.id != "" %}<a href="assets/papers/{{ pub.id }}.pdf" target="_blank" rel="me noopener noreferrer"><img src="logos/pdf.png" height="12px" style="margin-inline-start: 0.75em" alt="pdf"/></a>{% endif %}</li>
{% assign pubCounter = pubCounter | plus:1 %}
{% endfor %}
</ol>
</details>