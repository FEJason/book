# 隐藏 gitbook Published with GitBook

- 在项目中创建_layouts->website->summary.html
- summary.html内容如下

```
{% macro articles(_articles) %}
    {% for article in _articles %}
        <li class="chapter {% if article.path == file.path and not article.anchor %}active{% endif %}" data-level="{{ article.level }}" {% if article.path %}data-path="{{ article.path|resolveFile }}"{% endif %}>
            {% if article.path and getPageByPath(article.path) %}
                <a href="{{ article.path|resolveFile }}{{ article.anchor }}">
            {% elif article.url %}
                <a target="_blank" href="{{ article.url }}">
            {% else %}
                <span>
            {% endif %}
                    {% if article.level != "0" and config.pluginsConfig['theme-default'].showLevel %}
                        <b>{{ article.level }}.</b>
                    {% endif %}
                    {{ article.title }}
            {% if article.path  or article.url %}
                </a>
            {% else %}
                </span>
            {% endif %}

            {% if article.articles.length > 0 %}
            <ul class="articles">
                {{ articles(article.articles, file, config) }}
            </ul>
            {% endif %}
        </li>
    {% endfor %}
{% endmacro %}

<ul class="summary">
    {% set _divider = false %}
    {% if config.links.sidebar  %}
    {% for linkTitle, link in config.links.sidebar  %}
        {% set _divider = true %}
        <li>
            <a href="{{ link }}" target="_blank" class="custom-link">{{ linkTitle }}</a>
        </li>
    {% endfor %}
    {% endif %}

    {% if _divider %}
    <li class="divider"></li>
    {% endif %}

    {% for part in summary.parts %}
        {% if part.title %}
        <li class="header">{{ part.title }}</li>
        {% elif not loop.first %}
        <li class="divider"></li>
        {% endif %}
        {{ articles(part.articles, file, config) }}
    {% endfor %}

    <li class="divider"></li>

    <!--<li>-->
        <!--<a href="https://www.gitbook.com" target="blank" class="gitbook-link">-->
            <!--{{ "GITBOOK_LINK"|t }}-->
        <!--</a>-->
    <!--</li>-->
</ul>

```
- 注释掉的就是Published with GitBook可以隐藏也可修改链接
- 重启gitbook serve