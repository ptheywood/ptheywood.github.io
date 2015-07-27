---
layout: default
title: Demonstrating | ptheywood.uk
---

<section id="demonstrating" class="content">
    <div class="wrapper">
        <div class="container-fluid">
            <div class="row">
                <div class="col-xs-12">
                    <h2 class="sub-header">Demonstrating</h2>
                    <p class="text-left text-center-xs">
                        As a PhD student I have the opportunity to demonstrate lab sessions for taught students and outreach events.
                    </p>
                    <p class="text-left text-center-xs">
                        So far I have demonstrated for the following:
                        <ul class="demonstrating-list">
                        {% for year in site.data.demonstrating %}
                            <li>
                                <h4 class="sub-header">{{ year.year }}</h4>
                                <ul>
                                    {% for event in year.events %}
                                    <li>
                                        {{ event }}
                                    </li>
                                    {% endfor %}
                                </ul>
                            </li>
                        {% endfor %}
                        </ul>
                    </p>
                </div>
            </div>
        </div>
    </div>
</section>
