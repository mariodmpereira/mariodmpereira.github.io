---
nav_order: 1
layout: page
title: Getting Started
permalink: /jekyll/getting-started/
parent: Jekyll
---

# {{ page.parent }} - {{ page.title }}

I strongly recommend you to go through their {{ site.data.links.jekyll_steps }} before anything else, to have a basic understanding of how {{ site.data.bolded.jekyll }} works.

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

Now you can play with {{ site.data.bolded.jekyll }} to take full advantage of what you've learned while reading the {{ site.data.links.jekyll_steps }}.

I'm not going to go into more details here because by default, {{ site.data.bolded.jekyll }} uses a theme called **Minima**, and I choose another one. I want to show you how can you install any {{ site.data.links.jekyll_themes }} to build something similar to this page you are seeing now.

Then, you can host it on {{ site.data.bolded.github_pages }} for free like explained on {{ site.data.repositories.main.github_pages.home }}.

[Remote Themes]({{ site.data.repositories.main.github_pages.jekyll.themes_url }}){: .btn .btn-purple }

{% include examples-repository.markdown %}
- {{ site.data.repositories.examples.jekyll.myblog }}

{% include references.markdown %}

- {{ site.data.links.jekyll }}