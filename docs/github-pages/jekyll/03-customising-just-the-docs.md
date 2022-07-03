---
nav_order: 3
layout: page
title: Customising Just the Docs
permalink: /github-pages/jekyll/customising-just-the-docs/
parent: Jekyll
grand_parent: GitHub Pages
---

# {{ page.parent }} - {{ page.title }}

Before any customisation, I'm going to duplicate the directory **my-blog-just-the-docs-barebones** and name it **my-blog-just-the-docs-customised**.

## Changing to the dark theme

Yes, I'm one of those programmers.

> ### **_config.yml**
```yml
color_scheme: dark
```

Reboot your application and reload the page, you're welcome.

## Website Metadata

You can change all of the metadata about your website, I removed all of the comments because I link to keep things clean, my `_config.yml` file is as follows.
> ### **_config.yml**
```yml
color_scheme: dark
title: My Blog
email: mariodmpereira@gmail.com
description: >-
  This is my personal Developer Handbook to keep track of my learnings.
# baseurl: ""
url: "http://mariodmpereira.github.io/"
github_username:  mariodmpereira
remote_theme: just-the-docs/just-the-docs
plugins:
  - jekyll-feed
```

Please be advised that if you don't use a `baseurl` you should remote or comment that line. Trust me, it already caused me a lot of headaches trying to figure out why the website was misbehaving.

You can now select anywhere on your markdown files one of these yaml keys using the {{ site.data.bolded.liquid }}, that comes with {{ site.data.bolded.jekyll }} out of the box.

As an example, if you want to render the title of the site that you wrote on `_config.yml`, all you to need to do is this.

```markdown
{{ "{{ page.title " }}}}
```
## Favicon

Download any **favicon** and put it in the root folder of the project. 

Refresh, voilà.

![](/assets/images/jekyll/just-the-docs-favicon-01.png)

## Homepage title

At the time of writing this post, this theme contains a small issue.

If you look at the screenshot above for the **favicon**, you will notice there's a hyphen before the page name. 

{{ site.data.bolded.just_the_docs }} remote theme's [`head.html`](https://github.com/just-the-docs/just-the-docs/blob/main/_includes/head.html) is expecting both a `site.title` and a `page.title` for the its **HTML** `<title>` tag.

> ### **head.html**
> ```html
> <title>{{ "{{ page.title " }}}} - {{ "{{ site.title " }}}}</title>
> ```

Open your `index.markdown` on the root of the project and you will notice it only has a comment and a `layout:home` inside the {{ site.data.bolded.front_matter }} section. I removed the comment and added this line `title: Home`.

> ### **index.markdown**  
```markdown
---
layout: home
title: Home
---
```

Refresh and you should see the change.

![](/assets/images/jekyll/just-the-docs-page-title-01.png)

## Side Navigation
### Hide Pages

You probably noticed that after the last step, the ``Home`` navigation appeared on the side navigation. That's because {{ site.data.bolded.just_the_docs }} searches everywhere on the project for any markdown file inside a {{ site.data.bolded.front_matter }} section for a `title`, and considers it as part of the side navigation.

If you want to hide it from the side navigation you can add this extra line `nav_exclude: true`.

> ### **index.markdown**  
```markdown
---
layout: home
title: Home
nav_exclude: true
---
```

### Add Pages

As just explained in the previous section, you can now duplicate the `index.markdown` and call it `blog.markdown`. Change it's `title` to Blog and remove the ``nav_exclude: true`. This new page should now appear on the side navigation.

Tipically I store all the new pages under the `/docs` directory to keep the project structure organized, but you can leave them at the root of the project if you want. I'm going to move this `blog.markdown` I created inside `/docs/blog`

> ### **index.markdown**  
```markdown
---
layout: home
title: Blog
---
```

### Navigation Structure

I think that the [Just the Docs - Navigation Structure](https://just-the-docs.github.io/just-the-docs/docs/navigation-structure/) is well explained, with plenty of examples on how to make proper side navigation.

I added a few examples to the examples repository.

### Auxiliary Links (Top Navigation)

The same goes for this, you can check [Just the Docs - Aux links](https://just-the-docs.github.io/just-the-docs/docs/configuration/#aux-links) to simulate top navigation.

I added a few examples to the examples repository as well.

### Permalinks

You can easily add a permalink to any page by adding `permalink: /url` to any page's {{ site.data.bolded.front_matter }}.

### Side Navigation Order

To order pages on the side navigation, you need to use `nav_order` on each page's {{ site.data.bolded.front_matter }}.

It accepts numbers and it's from lowest to highest, first to last.

First element example: `nav_order: 1`  
Second element example: `nav_order: 2`  
Third element example: `nav_order: 3`

## Conclusion

You should have all the information you need to avoid the same mistakes I did, and to get started with your {{ site.data.bolded.jekyll }} and {{ site.data.bolded.just_the_docs }} static page on {{ site.data.bolded.github_pages }}. 

{% include examples_repository.markdown %}
- {{ site.data.devugger.examples_repository.just_the_docs_customised }}

{% include references.markdown %}

- {{ site.data.links.favicon }}
- {{ site.data.links.front_matter }}
- {{ site.data.links.liquid }}