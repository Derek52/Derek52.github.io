---
title: "Rewriting My Blog With Hugo"
date: 2023-02-07T22:53:34-05:00
slug: migrating-my-blog-to-hugo
draft: false
---

I've had my own little blog for several years, and it has been, annoying. I was on a DIY kick and built my blog from scratch using the Ruby gem, [Sinatra](https://sinatrarb.com/).
Now, Sinatra is awesome, and I had fun writing my site from scratch, but, it was the wrong solution for me. It was over-engineered and was too much work to maintain. The downsides were so severe, that for months now, I've mostly been avoiding using it.

So, I made a new blog, this one, with a static site generator called [Hugo](https://gohugo.io/). Moving away from the Ruby version of my site had trade-offs, but, for a blog migrating to Hugo was the right move.


## Why a Static Site Generator?

Static site generators are aptly named tools that take layout files, content, and other random stuff you want to throw at them, and then spits out a working website made up of a bunch of HTML files. The first benefit I get from this is speed. A static site made up of nothing but HTML pages is faster than my server side app that has to run Ruby code. Also, having a site of pure HTML is great for search engine optimization. You can add SEO to dynamic web apps, but it is more involved than when using static web pages.

Another perk is that hosting this site is now cheaper for me. It's free actually, thanks to [Github pages](https://pages.github.com/). Previously, I was hosting my blog on a self managed VPS via [Linode](linode.com). That VPS only cost me 5 bucks a month(and I was running more than one thing on it), but, free still manages to beat that. Also, it's just so much simpler. Provisioning a Linux VPS, installing Ruby and Sinatra, and configuring a server for web hosting is a bit of a chore. I'll say, I am a bit of an oddball, in that I actually enjoy that chore a little. But, I don't think you would enjoy manually configuring a remote server as much as I do. Github pages is just easy. Using a pre-configured Github action, I now have a CI/CD pipeline that will re-build and re-deploy my site whenever I push new commits to its Github repo. For free. It is awesome.

Finally, the biggest benefit of using a static site generator, is the content management. This was the most painful part about using the Ruby version of this blog. I had a basic text editor on my site, and my blog posts would be saved to a PostgreSQL database. In Hugo, my blog posts are in markdown files in a directory in my repo. Inside my site's directory, I can open up a terminal and run `hugo new posts/my-new-post.md` to create a markdown file for a new post. Then, after I've written it, I just commit it in git and publish it by pushing it to my Github.

This is a better writing experience than with my site, and a better backup experience. Backing up a PostgreSQL table isn't hard, but it is more work than simply checking my writing into git. Also, having my posts in plaintext markdown files will save me a step or two should I ever decide to move to a different static site generator or, god forbid, write my blog as another web app.(I have been wanting to learn more [Phoenix](https://www.phoenixframework.org/))


## Why Hugo?

Speaking of different static site generators, Hugo is not the only one available. When I decided to move my blog over, I experiemented with Hugo and [Jekyll](https://jekyllrb.com/). These appear to be the most popular tools in this space. On most of the lists I looked at Jekyll was the most popular, with Hugo following right behind. Jekyll is written in Ruby, and is the default static site generator that Github pages is setup for. Hugo is written in Go, and took about five minutes to configure Github pages to work with. Jekyll works very well, and being that I love Ruby, it is probably what I should have stuck with.

But, to try something new, I gave Hugo a go, and decided to stick with it. The structure of a Hugo site is a little more complicated than Jekyll, and it takes a little bit longer to get up and running with, but, not *that* much longer. One of Hugo's main selling points is speed. I will vouch for the fact that when running the site locally, my Hugo server would build and re-build on changes several times faster than my Jekyll server. However, this was the difference between one second, and three or four seconds, so I didn't really care that Jekyll was slower to build. The speed of the website these two tools produce shouldn't have a speed difference a human can notice, since they are both static HTML.

Realistically, I made the choice to use Hugo over Jekyll due to some personal decisions over very small things. They are both excellent, and both are open source, which is important to me. There are lots of static site generators out there, and I'm sure a lot of them are good. I've been hearing good things about [Gatsby](gatsbyjs.com) for years, and while I was writing this article, I came across [Pelican](getpelican.com) which I now want to take for a spin. If you think a static site generator is the right tool for you, you can probably try out any of them, and get a basic site up and running pretty quickly.

### Final Recommendation

Personally, I would recommend Jekyll or Hugo, because they are so popular and have the biggest communities of users, but, that is me. Even though I went with Hugo, I may even recommend Jekyll to you, because it was a bit easier and more pleasant to initially get working.

Whatever the case, I hope that the next time you have a simple website you need to whip up, you ask yourself, "Does this need to be a dynamic webapp?". And if the answer is "no" or "maybe not", I hope you consider using a static site generator. Should you choose to use Hugo, you can look at the repo for this site [here](https://github.com/Derek52/Derek52.github.io). I have a feeling The [Hugo quickstart guide](https://gohugo.io/getting-started/quick-start/) would probably be more helpful to you though.