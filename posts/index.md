---
layout: default
title: Posts | ptheywood.uk
---
<section id="posts" class="content">
    <div class="wrapper">
        <div class="container-fluid">
            <div class="row">
                <div class="col-xs-12">
                    <h2>Posts</h2>
                    <p>
                    </p>
                    {% if site.posts.size > 0 %}
                        <div class="list-group">
                            {% for post in site.posts %}
                            <a class="list-group-item {% if url == post.url %} active{% endif %}>" href="{{post.url}}" title="{{post.title}}">
                                <em>{{post.date | date: '%d %B %Y'}}</em>
                                -
                                <strong>{{post.title}}</strong>
                            </a>
                            {% endfor %}
                        </div>
                    {% else %}
                        <p>
                            Sorry, there are currently no posts to display.
                        </p>
                    {% endif %}
                </div>
            </div>
        </div>
    </div>
</section>
