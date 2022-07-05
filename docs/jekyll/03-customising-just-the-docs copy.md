---
layout: page
title: Customising Just the Docs
permalink: /jekyll/customising-just-the-docs/
parent: Jekyll
nav_order: 3
---

# {{ page.parent }} - {{ page.title }}

Before any customisation, duplicate the directory **my-blog-just-the-docs-barebones** and name it **my-blog-just-the-docs-customised**.

I should warn that any change you make to `_config.yml` will only be applied when you restart the server, even if you ran it with `--livereload`.

## Changing to the dark theme

Yes, I'm one of those programmers.

> ### **_config.yml**
```yml
color_scheme: dark
```

Reboot your application and reload the page, you're welcome.

## Website Metadata

You can change any metadata regarding your website, I removed all of the comments because I like to keep things clean, my `_config.yml` file is as follows.
> ### **_config.yml**
```yml
color_scheme: dark
title: My Blog
email: mariodmpereira@gmail.com
description: >-
  This is my personal Developer Handbook to keep track of my learnings.
# baseurl: ""
url: "http://www.mariodmpereira.com/"
github_username:  mariodmpereira
remote_theme: just-the-docs/just-the-docs
plugins:
  - jekyll-feed
```

Please be advised that if you don't use a `baseurl` you should **remote** or **comment that line**. Trust me, it already caused me a lot of headaches trying to figure out why the website was misbehaving, and I still haven't figured out what was the problem.

Not only did you set up some metadata for your website (like the page title), but you can now select these **yml** keys using the {{ site.data.bolded.liquid }}, that comes with {{ site.data.bolded.jekyll }} out of the box.

As an example, if you want to render the title of the site you have on `_config.yml`, all you to need to do is write this on any {{ site.data.bolded.html }} or {{ site.data.bolded.markdown }} file.

```markdown
{{ "{{ page.title " }}}}
```
## Favicon

Download any **favicon** and put it in the root folder of the project. 

Refresh, voilà.

![Just the Docs Favicon - 01](/assets/images/jekyll/just-the-docs-favicon-01.png)

## Homepage title

At the time of writing this post, this theme contains a "small issue".

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

![Just the Docs Page Title - 01](/assets/images/jekyll/just-the-docs-page-title-01.png)

## Side Navigation
### Hide Pages

You probably noticed that after the last step, the ``Home`` navigation appeared on the side navigation. That's because {{ site.data.bolded.just_the_docs }} searches on the project for any markdown file inside a {{ site.data.bolded.front_matter }} section for a `title`, and considers it as part of the side navigation.

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

As just explained in the previous section, you can now duplicate the `index.markdown` and call it `blog.markdown`. Change its `title` to Blog and remove the `nav_exclude: true`. This new page should now appear on the side navigation.

Typically I store all the new pages under the `/docs` directory to keep the project structure organized, but you can leave them at the root of the project if you want. I'm going to move this new `blog.markdown` file into `/docs/blog`

> ### **blog.markdown**  
```markdown
---
layout: home
title: Blog
---
```

### Permalinks

You can easily add the path to any page by adding `permalink: /url` to any page's {{ site.data.bolded.front_matter }}.

> ### **blog.markdown**  
```markdown
---
layout: home
title: Blog
permaling: /blog
---
```

### Navigation Structure

I think that the [Just the Docs - Navigation Structure](https://just-the-docs.github.io/just-the-docs/docs/navigation-structure/) is well explained, with plenty of examples on how to make proper side navigation.

### Auxiliary Links (Top Navigation)

The same goes for this, you can check [Just the Docs - Aux links](https://just-the-docs.github.io/just-the-docs/docs/configuration/#aux-links) to simulate top navigation.

### Side Navigation Order

To order pages on the side navigation, you need to use `nav_order` on each page's {{ site.data.bolded.front_matter }}. For example, for the first page vertically you would use `nav_order: 1`, for the fourth `nav_order: 4`.

> ### **blog.markdown**  
```markdown
---
layout: home
title: Blog
permaling: /blog
nav_order: 4
---
```

[Closing Remarks]({{ site.data.repositories.main.github_pages.just_the_docs.closing_remarks_url }}){: .btn .btn-purple }

{% include examples-repository.markdown %}
- {{ site.data.repositories.examples.just_the_docs.customised }}

{% include references.markdown %}

- {{ site.data.links.favicon }}
- {{ site.data.links.front_matter }}
- {{ site.data.links.just_the_docs }}
- {{ site.data.links.liquid }}