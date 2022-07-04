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
# If you have an error because of webrick, execute this and try to run the server again.
bundle add webrick
```

Now navigate to your {{ site.data.links.localhost }} and you should see something similar to this.

![Jekyll Live - 01](/assets/images/jekyll/jekyll-live-01.png)

Now you can play with {{ site.data.bolded.jekyll }} to take full advantage of what you've learned while reading the {{ site.data.links.jekyll_steps }}.

I'm not going to go into more details here. I want to show you how can you install any of the {{ site.data.links.jekyll_themes }} to build something similar to this page you are seeing now, and then how to host it on {{ site.data.bolded.github_pages }} for free. There are a ton of themes you can choose from, choose wisely. Before deciding, check the next section first.

[Remote Themes]({{ site.data.devugger.links.jekyll_themes_url }}){: .btn .btn-purple }

{% include examples-repository.markdown %}
- {{ site.data.devugger.examples_repository.myblog }}

{% include references.markdown %}

- {{ site.data.links.jekyll }}