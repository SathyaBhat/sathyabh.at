+++
author = "Sathyajith Bhat"
categories = ["Meta"]
tags = ["blogging", "blog-questions"]
places = "Sydney"
type = "post"
url = "/blogging-challenge-blog-questions/" 
title = "A challenge of blog questions"
date = 2025-02-23T12:00:00Z
summary = "Remember blog-tags? Here's answering some questions on how and why I started blogging."
+++

# A challenge of blog questions

Ooh, we’re doing tag-you’re-answering. It’s been so long since I’ve done something like this, brings back fond memories. Thank you, [Kris](https://www.web-goddess.org/archive/54805) for the tag!

**Why did you start blogging in the first place?**

I have two blogs - a personal blog ([this one](https://sathyabh.at)) and my [tech blog](https://sathyasays.com). I had some free time since the joining date for my first job was a few months away. Armed with boredom, an Internet connection and an ample amount of free time, I started [Sathya Says](https://sathyasays.wordpress.com/) on WordPress.com hosting. I was experimenting a lot with desktop Linux, so I started writing about it - lots of reviews, opinions and troubleshooting posts while I distro hopped. I started doing some link posts, opinion posts and also started covering a lot of Linux news. A lot of the writing was selfish - for my reference but it started picking up among the [blogosphere](https://en.wikipedia.org/wiki/Blogosphere) well - my small blog was attracting tens of thousands of views per month(which surprised me quite a lot since I focused on Desktop Linux, a tiny niche). I experimented with AdSense in an attempt to monetize it and managed to hit the $100 threshold in about 4 months. I removed AdSense soon after, there was just no point with such abysmal CTRs. At some point, I started writing more about my personal life as well and wanted to keep those two topics separate, thus my personal blog was spun off.

**What platform are you using to manage your blog and why did you choose it? Have you blogged on other platforms before?**

I started blogging with [WordPress about 18 years ago](https://sathyasays.com/2007/05/27/hello-world-2/). Soon after, I came to know about domains, shared hosting and self-hosted WordPress and with my first ever salary, purchased sathyasays.com. The shared hosting served me quite well. As I started moving away from my DBA role into DevOps role, I got a Digital Ocean VPS to experiment with Linux servers. The droplet hosted both the blogs and a few other small services till about 2019 when I got tired running, maintaining and securing my WordPress install. I was going through a major blogging rut. That, along with my SRE job (which involved week-long 24x7 on-call shifts every 7 weeks or so), the cross-continental move [from India to Romania](https://sathyabh.at/2020/01/08/salut-bucharest/), authoring “[Practical Docker With Python](https://sathyasays.com/2018/10/02/so-i-wrote-a-book-presenting-practical-docker-with-python/)” and running AWS User Groups meant that I barely had time to write, so I migrated the sites to a [static site powered by Hugo](https://sathyasays.com/2020/08/28/migrating-moving-your-wordpress-blog-to-hugo/) hosted on Netlify. Netlify hosted worked fine till they started turning the screws on free hosting - reducing available bandwidth, increasing the prices and other general shenanigans that annoyed me. I had some AWS credits and wanted to understand how [AWS Amplify Hosting](https://aws.amazon.com/amplify/hosting/) worked, so I migrated the blogs to Amplify hosting and it’s been running there since then.

**How do you write your posts? For example, in a local editing tool, or in a panel/dashboard that’s part of your blog?**

I mostly write on [my desktop](https://sathyabh.at/setup/) using Neovim/[Lazyvim](https://www.lazyvim.org/) as my editor. Hugo is a static site generator which converts Markdown files to websites, so I don’t need any special panels/editors - any text editor will do. I’ve experimented with static CMS such as [Decap CMS](https://decapcms.org/docs/intro/) (formerly Netlify CMS) but didn’t find it to be of much use. My general workflow is to write my post as Markdown, commit to my GitHub repos (I have separate repos for both sites) and have Amplify handle the rest of the headache of build, publish and invalidate cached files.
When I’m traveling for work, I ssh into my [NAS](https://sathyabh.at/nas) from my iPad and compose my posts using Neovim. I've also used [vscode.dev](https://code.visualstudio.com/docs/editor/vscode-web) to edit my posts when I’m on the go as well.

**When do you feel most inspired to write?**

Inspiration has been hard to come by. During my younger days, I write multiple times a day/week and didn’t care much for public opinion. In today’s world I am a lot more careful about what I write and that meant that I felt like I couldn’t share what I wanted.

About two years ago, inspired by [Thej’s](https://thejeshgn.com/tag/weekly-notes/) weekly notes I [started writing](https://sathyabh.at/2023/01/21/weekly-notes-03-2023/) a weekly notes post every Sunday to force myself to write again. This has now became a weekly habit and I write the notes every Sunday. I have a lot more posts in my drafts, I’ve been sitting on them for far too long because I felt it wasn’t worth sharing. Working on getting the confidence back to share what I have written.

**Do you publish immediately after writing, or do you let it simmer a bit as a draft?**

I’ve got way too many posts sitting in drafts and I have accepted that keeping them in drafts to simmer and improve over time is a sure shot way of never publishing it, so now I just publish it immediately.

**What’s your favorite post on your blog?**

Oh there’s so many - I love my [travel](https://sathyabh.at/categories/travel/) posts (there’s many that I didn’t get to finishing) and some of my [earliest writing](https://sathyabh.at/categories/life/page/14/) about my experiences as I moved out of house and went from the west to the east coast of India and fantastic, but I think this post about my [first ever International flight](https://sathyabh.at/categories/travel/) which also became a mini tweetup is probably my favorite. Another favorite is my rant about finishing college - getting that off my chest and onto [writing](https://sathyabh.at/2007/06/10/its-all-over/) felt so good.

**Any future plans for your blog? Maybe a redesign, a move to another platform, or adding a new feature?**

Nothing for now - I might consider moving the blogs to Ghost - my weekly notes for example are delivered as email using [Substack](https://sathyabhat.substack.com) and I don’t want to import and duplicate my content to another platform that I don’t control when I can have everything in a single platform that I run and control.

**Who’s next?**

I’m hoping some of my blog readers can take this up: [Thej](https://thejeshgn.com/), [Shrayas](https://shrayas.com), [Divya](https://divyashivaram.substack.com/), [Ninad](https://ninad.pundaliks.in/) and [Bibhas](https://bibhasdn.com/).

Cheers
