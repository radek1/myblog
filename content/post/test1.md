---
title: "Installing Hugo and first post"
date: 2021-01-12T18:57:09-08:00
draft: false
---

First post: How I setup this blog.
===========
# Getting domain
I just hopped to `googledomains.com` and bought `sedlacik.dev` domain, $12/year

# Installing Hugo
Download Win 64bit binary (in my case) from https://gohugo.io/getting-started/installing/ and extract to a suitable directory.
I added hugo executable to PATH environment variable. Another folder created is `Websites` where all (one) websites will reside.
We need to install `git` as well but I had it from before.

# Creating first site and installing Hugo theme
As recommended in other Hugo tutorials I'm starting with Ananke theme.
`cd` to `Websites`
```shell
cd Websites
hugo new site myblog
cd myblog
git init
git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
```


# Customizing Ananke theme
Copy `config.toml` from `theme/ananke/exampleSite` folder of this theme to root of the `myblog`. 
I modified it as below:

```
title = "Test Blog"
baseURL = "/"
languageCode = "en-us"
theme = "ananke"


DefaultContentLanguage = "en"
SectionPagesMenu = "main"
Paginate = 8 # this is set low for demonstrating with dummy content. Set to a higher number
googleAnalytics = ""
enableRobotsTXT = true

[sitemap]
  changefreq = "monthly"
  priority = 0.5
  filename = "sitemap.xml"

[params]
  favicon = ""
  site_logo = ""
  description = "My blog."
  facebook = ""
  twitter = "https://twitter.com/GoHugoIO"
  instagram = ""
  youtube = ""
  github = ""
  gitlab = ""
  linkedin = ""
  mastodon = ""
  slack = ""
  stackoverflow = ""
  rss = ""
  # choose a background color from any on this page: http://tachyons.io/docs/themes/skins/ and preface it with "bg-"
  #background_color_class = "bg-transparent"
  cover_dimming_class =  "bg-transparent"
  recent_posts_number = 2
```
  
Line `cover_dimming_class =  "bg-transparent"` will stop hero image from dimming (darkening).

Copy all from `themes/ananke/exampleSite/content/en` to `myblog/content`

`cp -r themes/ananke/exampleSite/content/en/* content`

put hero image (`Barn.png` in my case) to `/static/images`

Change `content/_index.md` to something reasonable

Change `content/post/_index.md` to something reasonable

Change `content/about/_index.md` to something reasonable

# Run Hugo site
`hugo server`
as indicated open http://localhost:1313/ in browser

# First real content
`hugo new post/test1.md`

edit `test1.md`

run again hugo server, with drafts enabled: 

`hugo server -D`





