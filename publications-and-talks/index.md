---
layout: default
title: Publications &amp; Talks | ptheywood.uk
---

<section id="publications" class="content">
    <div class="wrapper">
        <div class="container-fluid">
            <div class="row">
                <div class="col-xs-12">
                    <h2 class="sub-header"><span>Publications</span></h2>
                    <ul class="list-unstyled">
                    {% for year in site.data.publications %}
                        <li>
                            <h3>{{ year.year }}</h3>
                            <ul>
                                {% for publication in year.publications %}
                                <li>
                                    {% if publication.authors %}
                                        {{ publication.authors }}
                                    {% endif %}
                                    {% if publication.title %}
                                        "{{ publication.title }}"
                                    {% endif %}
                                    {% if publication.journal %}
                                        {{ publication.journal }}
                                    {% endif %}
                                    {% if publication.href %}
                                        (<a href="{{ publication.link }}" target="_blank">View</a>)
                                    {% endif %}
                                </li>
                                {% endfor %}
                            </ul>
                        </li>
                    {% endfor %}
                    </ul>
                </div>
            </div>
        </div>
    </div>
</section>

<section id="talks" class="content">
    <div class="wrapper">
        <div class="container-fluid">
            <div class="row">
                <div class="col-xs-12">
                    <h2 class="sub-header"><span>Talks</span></h2>
                    <ul class="list-unstyled">
                        {% for talk in site.data.talks %}
                        <li>
                            {{ talk.date }}:
                            <a href="{{ talk.event_url }}">
                            {{ talk.event }}
                            </a>
                            <strong>{{ talk.title }}</strong>
                            {{ talk.note }}
                        </li>
                        {% endfor %}
                    </ul>
                </div>
            </div>
        </div>
    </div>
</section>
