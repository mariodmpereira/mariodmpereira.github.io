---
nav_order: 1
layout: page
title: Getting Started
permalink: /github-pages/getting-started/
parent: GitHub Pages
---

# {{ page.parent }} - {{ page.title }}

Does this sound simple to you?

> *Hosted directly from your GitHub repository. Just edit, push, and your changes are live.*

It is indeed. You can follow this very simple [step-by-step guide]({{ site.data.links.github_pages_url }}) on how to serve a simple markdown file.

But if you want an overall overview, you can turn one of your {{ site.data.bolded.github }} repository's into a static hosted website on {{ site.data.bolded.github_pages }}, but typically the idea is you create a new repository with the name `yourgit.github.io`. 

Let's assume from now on I'm doing it. My username is `{{ site.data.author.username }}`, so the repository name would be `{{ site.data.devugger.repository_name }}`.

Select the checkbox that says `Add a README file` and then click `Create repository`.

Please take into account that it may take a few minutes for it to be live. To check how is the deployment status, go to your repository's root and there should be a yellow circle just near the commit hash on the right, you can click it to know more information about the deploy status.

![GitHub Deploying - 01](/assets/images/github/github-deploying-01.png/)

Once that circle is green you are good to go.

![GitHub Deploying - 02](/assets/images/github/github-deploying-02.png)

Navigate to {{ site.data.links.home }} and you should see the link of your repository because {{ site.data.bolded.github_pages }} is rendering your `README.md` file.

![GitHub Deploying - 03](/assets/images/github/github-deploying-03.png)

Try adding any text to that `README.md` file and committing the changes. As soon as the deployment is ready, you can refresh your browser at {{ site.data.devugger.links.home }} and you should see your changes.

But that's pretty boring, right? It's just a single markdown file being rendered to the browser. 

Fear not! You can upload any static website, using plain {{ site.data.bolded.html }}, {{ site.data.bolded.css }} and {{ site.data.bolded.javascript }}, or using any framework like {{ site.data.links.bootstrap }}, {{ site.data.links.bulma }}, {{ site.data.links.tailwind }}, among others.

I'm gonna suggest another alternative below.

[Meet {{ site.data.bolded.jekyll }}]({{ site.data.devugger.links.jekyll_url }}){: .btn .btn-purple }

{% include references.markdown %}

- [GitHub](https://github.com/)
- [GitHub Pages](https://pages.github.com/)