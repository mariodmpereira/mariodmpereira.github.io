---
nav_order: 2
layout: page
title: Remote Themes
permalink: /jekyll/remote-themes/
parent: Jekyll
---

# {{ page.parent }} - {{ page.title }}

{{ site.data.bolded.jekyll }} supports **Gem based themes** and **remote themes**. [Its website]({{ site.data.links.jekyll_themes_url }}) warns you that {{ site.data.bolded.github_pages }} does not have support for many **Gem based themes** straight away:

> *If you’re publishing your {{ site.data.bolded.jekyll }} site on {{ site.data.bolded.github_pages }}, note that {{ site.data.bolded.github_pages }}  supports only some gem-based themes. {{ site.data.bolded.github_pages }} also supports using any theme hosted on {{ site.data.bolded.github }} using the remote_theme configuration as if it were a gem-based theme.*

Since all the **remote themes** that are hosted on {{ site.data.bolded.github }} are supported by {{ site.data.bolded.github_pages }}, we're going to go with one of them.

I'm going to pick up where we left off in the previous section on the **myblog** project, but I'm going to duplicate the project directory **myblog** and call it **my-blog-just-the-docs-barebones**. I did this just so I can keep multiple copies of this walkthrough on my [examples project]({{ site.data.devugger.examples_repository.jekyll_url }}).

After consering a few themes for this website I choose {{ site.data.links.just_the_docs }}.

As soon as you enter their website, you see some that you can use a **remote theme** or a **Gem based**. Copy the **remote_theme** line and replace the `_config.yml` line `theme: minima` (or just comment this line) with the one you just copied.

Then on the **Gemfile** delete or comment the line `gem "minima", "~> 2.5"`.

> ### **_config.yml**
```yml
# theme: minima
remote_theme: just-the-docs/just-the-docs
```

> ### **Gemfile**
```yml
# gem "minima", "~> 2.5"
```

If you try running the application now with `bundle exec jekyll serve --livereload` you should have some errors about a missing dependency. But when you add that dependency to the **Gemfile**, the same error may appear from others.

My suggestion is to try this:

> ### **terminal**
```bash
# Stage all your changes on Git.
git add -all
>
# Force the bundler to fetch all remote sources.
bundle install
>
# Check what changed on your Gemfile.
git diff
```

This will show you what dependencies you are missing.

![Jekyll Missing Dependencies - 01](/assets/images/jekyll/jekyll-missing-dependencies-01.png)

Go to your project **Gemfile** and all these dependencies to the **group :jekyll_plugins**. On my case, I added `gem "jekyll-include-cache"`, `gem "jekyll-include-cache"` and `gem "rake"`. 

> ### **Gemfile**
```ruby
...
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-remote-theme"
  gem "jekyll-include-cache"
  gem "jekyll-seo-tag"
  gem "rake"
end
...
```

Try starting the server with bundle `exec jekyll serve --livereload` and it should boot your website.

Navigate to your {{ site.data.links.localhost }} and you should see your website live.

![Jekyll Live - 02](/assets/images/jekyll/jekyll-live-02.png)

It's done, your website is now live. But still looks a bit boring, so in the next section, I will try to give you a basic understanding of how to quickly customise this theme to make it more appealing.

[Customising Just the Docs]({{ site.data.devugger.links.just_the_docs_customising_url }}){: .btn .btn-purple }

{% include examples-repository.markdown %}
- {{ site.data.devugger.examples_repository.just_the_docs_barebones }}

{% include references.markdown %}

- {{ site.data.links.just_the_docs }}
- {{ site.data.links.liquid }}