## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/tmaturi/try/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

{% assign tableItems = include.items | split: ", " %}
{% assign tableFileParam = {{include.file}} %}
{% assign tableFile = site.data[tableFileParam] %}

<table class="grid" style="width: 100%">
    <caption>{{include.caption}}</caption>
    <colgroup>
        <col width="20%" />
        <col width="65%" />
        <col width="15%" />
    </colgroup>
    <thead>
        <tr class="header">
            <th>Field</th>
            <th>Description</th>
            <th>Data Type</th>
        </tr>
    </thead>
    <tbody>
    {% for entry in tableItems %}
        <tr>
          <td>{{ tableFile[entry].field }}<br/>
          {% if tableFile[entry].required == true %}<span class="tableRequired">required</span>{% endif %}</td>
          <td>{{tableFile[entry]description}}
          {% if tableFile[entry].values != empty %}{{ tableFile[entry].values }}{% endif %}</td>
          <td>{{ tableFile[entry].type }}</td>
        </tr>
    {% endfor %}
    </tbody>
</table>
Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/tmaturi/try/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
