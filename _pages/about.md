---
layout: about
title: Home
permalink: /
description: Adam Poupard is a PhD candidate in ecological economics researching biodiversity policy, food systems, political economy, and macroeconomics.
og_image: /assets/img/adam-poupard.jpg
subtitle: PhD candidate in ecological economics at <a href="https://economix.fr/fr/membre/poupard-adam">EconomiX</a> and <a href="https://cesco.mnhn.fr/">CESCO</a>

profile:
  align: right
  image: adam-poupard.jpg
  image_circular: false
  more_info: >
    <p>Université Paris Nanterre</p>
    <p>Muséum national d'Histoire naturelle</p>
    <p>Paris, France</p>

selected_papers: false
social: false

announcements:
  enabled: false

latest_posts:
  enabled: false
---

I am a PhD candidate in ecological economics and political economy at Université Paris Nanterre (EconomiX) and the Muséum national d'Histoire naturelle (CESCO). My research examines the macroeconomic, institutional, and social dimensions of biodiversity conservation and food-security policies, with a particular focus on food social protection in France and Brazil.

Trained as an engineer-economist and environmental scientist at École Polytechnique, Sciences Po, and Sorbonne Université, I previously worked on ecological transition issues at the World Bank, CIRED, and I4CE. My current work studies how agroecological and biodiversity transitions can be made economically viable, socially just, and democratically governed.

You can find my publications under [Research]({% link _pages/research.md %}), my public-facing work under [Media]({% link _pages/media.md %}), and my teaching activities under [Teaching]({% link _pages/teaching.md %}).

Member of [CIRCEE](https://circee-ecol-econ.github.io/).

<div class="social mt-4" aria-label="Social profiles">
  <div class="contact-icons">
    {% if site.data.socials.linkedin_username %}
      <a
        href="https://www.linkedin.com/in/{{ site.data.socials.linkedin_username }}"
        title="LinkedIn"
        aria-label="LinkedIn"
        target="_blank"
        rel="noopener noreferrer"
      ><i class="fa-brands fa-linkedin" aria-hidden="true"></i></a>
    {% endif %}
    {% if site.data.socials.orcid_id %}
      <a
        href="https://orcid.org/{{ site.data.socials.orcid_id }}"
        title="ORCID"
        aria-label="ORCID"
        target="_blank"
        rel="noopener noreferrer"
      ><i class="ai ai-orcid" aria-hidden="true"></i></a>
    {% endif %}
    {% if site.data.socials.scholar_userid %}
      <a
        href="https://scholar.google.com/citations?user={{ site.data.socials.scholar_userid }}"
        title="Google Scholar"
        aria-label="Google Scholar"
        target="_blank"
        rel="noopener noreferrer"
      ><i class="ai ai-google-scholar" aria-hidden="true"></i></a>
    {% endif %}
    {% if site.data.socials.research_gate_profile %}
      <a
        href="https://www.researchgate.net/profile/{{ site.data.socials.research_gate_profile }}/"
        title="ResearchGate"
        aria-label="ResearchGate"
        target="_blank"
        rel="noopener noreferrer"
      ><i class="ai ai-researchgate" aria-hidden="true"></i></a>
    {% endif %}
  </div>
</div>

{% assign latest_news = site.data.research | concat: site.data.media | sort: "sort_date" | reverse %}

<section class="mt-5" aria-labelledby="last-news-title">
  <h2 id="last-news-title">Last news</h2>
  <div class="table-responsive">
    <table>
      <tbody>
        {% for item in latest_news limit: 5 %}
          {% if item.official_url %}
            {% assign item_type = "Research" %}
            {% assign item_date = item.year %}
            {% assign item_source = item.venue %}
            {% assign item_url = item.official_url %}
          {% else %}
            {% assign item_type = "Media" %}
            {% assign item_date = item.date %}
            {% assign item_source = item.outlet %}
            {% assign item_url = item.url %}
          {% endif %}
          <tr>
            <td class="text-nowrap align-top">{{ item_date }}</td>
            <td>
              <strong>{{ item_type }}</strong> · {{ item_source }}<br>
              <a href="{{ item_url }}" target="_blank" rel="noopener noreferrer">{{ item.title }}</a>
            </td>
          </tr>
        {% endfor %}
      </tbody>
    </table>
  </div>
  <p><a href="{% link _pages/research.md %}">All research</a> · <a href="{% link _pages/media.md %}">All media</a></p>
</section>
