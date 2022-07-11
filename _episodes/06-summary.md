---
title: "Summary and Wrap"
teaching: 5
exercises: 0
questions:
- "What did we discuss today?"
objectives:
- "Summarise and wrap up what was learnt during this workshop"
---

<h2>Key Points</h2>
<table class="table table-striped">
{% for episode in site.episodes %}
  {% unless episode.break %}
    <tr>
      <td class="col-md-3">
        <a href="{{ page.root }}{{ episode.url }}">{{ episode.title }}</a>
      </td>
      <td class="col-md-9">
        <ul>
        {% for keypoint in episode.keypoints %}
        <li>{{ keypoint|markdownify }}</li>
        {% endfor %}
        </ul>
      </td>
    </tr>
  {% endunless %}
{% endfor %}
</table>

> ## Question to audience 
> - How might you want to apply this in the future
{: .discussion}


> ## Course survey!
>
> **_Please_** fill out our **[course survey](https://sydney.au1.qualtrics.com/jfe/form/SV_9BvEIVKTpgQSRx4)** before you leave!
>
{: .testimonial}
