---
layout: page
title: Getting Started
permalink: /jekyll/getting-started/
parent: Jekyll
nav_order: 1
---

# {{ page.parent }} - {{ page.title }}

I strongly recommend you to go through their {{ site.data.links.jekyll_steps }} before anything else, to have a basic understanding of how **Jekyll** works.

Before that and as they advise on their {{ site.data.links.jekyll_docs }}, install all the  {{ site.data.links.jekyll_requirements }}.

After installing all the requirements, and according to the current {{ site.data.links.jekyll_docs }}:

> ### **terminal**
```bash
gem install jekyll bundler && jekyll new myblog && cd myblog
>
# Start the server with live reload activated.
bundle exec jekyll serve --livereload
>
# If you encounter any error related to webrick, execute this and try to run the server again.
bundle add webrick
```

Now navigate to your {{ site.data.links.localhost }} and you should see something similar to this.

![Jekyll Live - 01](/assets/images/jekyll/jekyll-live-01.png)

Now you can play with **Jekyll** to take full advantage of what you've learned while reading the {{ site.data.links.jekyll_steps }}.

I'm not going to go into more details here because by default, **Jekyll** uses a theme called **Minima**, and I choose another one. I want to show you how can you install any {{ site.data.links.jekyll_themes }} to build something similar to this page you are seeing now.

Then, you can host it on **GitHub Pages** for free like explained on {{ site.data.repositories.main.github_pages.home }}.

[Remote Themes]({{ site.data.repositories.main.github_pages.jekyll.themes_url }}){: .btn .btn-purple }

{% include examples-repository.markdown %}
- {{ site.data.repositories.examples.jekyll.myblog }}

{% include references.markdown %}

- {{ site.data.links.jekyll }}