---
layout: post
title:  "My discovery of publishing to Github Pages"
date:   2021-03-19 11:50:10 -0400
categories: github-pages jekyll update
---
Any web developer will tell you that there is always more to learn.

This week, I've been poking my head in the world of React with a dose of Redux. One of the
[React Tutorial for Beginners](https://www.taniarascia.com/getting-started-with-react/) included
steps for publishing your completed React app to GitHub pages, which is something I was vaguely
aware of, but had not explored before.

One of the first things I did was follow the
[instructions for creating a GitHub Pages site](https://docs.github.com/en/github/working-with-github-pages/creating-a-github-pages-site)
but this is a bit misleading.

> your repository must be named `<user>.github.io`

You don't necessarily want to do this. In the end, I deleted this repository, because it's not necessary,
and it led to a cycle of "deploy, refresh, scratch head", plus some attempts to try different branches on
my GitHub repositories. In the end, I'm not sure why the instructions are presented this way, or what this
specially named repo would be used for. For code pages, like React, you can just add the `gh-pages` package
to your project, tweak `package.json` with a few settings, and start using `npm build deploy`, and you'll
be able to see your published production build at `https://<github-username>.github.io/<repo-name>`. Or if
you're building a blog, you can create a repo for the blog, install a site generator (if you're going this
route), merge the completed blog files into your `gh-pages` branch, and it will also appear at the above
pattern. There may be a lag of a few minutes between the deploy command completing, or the merge of new blog
posts into your `gh-pages` branch, but if you're patient, you'll see the hosted, deployed fruit of your labor
on GitHub pages without much trouble at all.

Since custom domains are an option with GitHub pages, and I have some domain names I like to use for these
projects, I had to try this out as well. Again, the instructions aren't entirely clear. For a static web
site, you can create a file named `CNAME` (no extension) and put your domain in it (i.e. `subdomain.mydomain.tld`).
If you don't do this, but just use the repo settings at github.com, you may find that setting gets
overwritten. Similarly, with deployed production builds for a framework like React, you'll need this file, but
location of the file varies with each framework. In React, you'll want the file in your `/public/` folder, and
in Angular, you want it in `/src/`. I don't want to repeat all the steps to
[configuring a custom domain](https://docs.github.com/en/github/working-with-github-pages/configuring-a-custom-domain-for-your-github-pages-site),
but as a reminder, you'll also need to add the above `CNAME` to your DNS records.

Overall, the process isn't too difficult, but there are some odd sets of instructions out there, and like the
lesson of teaching a computer to make a sandwich, instructions that are followed literally can lead to some
strange effects! If you give this a try and run into any issues, shoot me an email and I'll do my best to help
you out!