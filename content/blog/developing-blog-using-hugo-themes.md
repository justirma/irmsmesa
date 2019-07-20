+++
categories = ["Tutorials"]
date = "2018-10-09"
title = "developing a blog using Hugo themes"
description = ""
featured = "pic01.jpg"
featuredalt = ""
featuredpath = "date"
linktitle = ""
slug = "Creation d'un nouveau theme"
type = "post"
+++

## Hugo: What’s that?

So what is [Hugo](https://gohugo.io/) you might ask? Hugo is a static site generator based off on HTML, CSS and maybe some JS for behavior additions. The themes are written in the Go Language. You may have heard of Jekyll, which another site generator. I had tried it before but I stopped working on the project and then heard about Hugo so decided to give it a shot. It’s 10x easier to setup than [Jekyll.](https://jekyllrb.com/) With Hugo it will make it super simple to create regular blog posts and not have to worry about Wordpres and all that comes with it. Just needed a simple blog page to share blog posts. Let’s go over my process in getting setup.

## Hugo Setup: Quick start

First I created a directory called “seshcollective” in my ~/Sites folder using the beginning steps [here](https://gohugo.io/getting-started/quick-start/) for creating a new site I’m keeping larger projects in the folder, while my practice projects are being stored in my ~/Projects. Prior, I was keeping my projects on my Desktop or in a folder on my Desktop called web but this was getting messy and cluttering up my Desktop. Not only that, but I was getting some Git help from Kevin at [AdelieWeb](http://adelieweb.com/) while working on one of his project assignments and he mentioned he keeps his code projects organized and I was like, **hey, that’s a great idea!** and so it began. Organization FTW. Back to Hugo.

## Hugo Themes: Keep it Minimal

After creating that folder, I kept using the [Quick Start](https://gohugo.io/getting-started/quick-start/) to follow the rest of the much needed steps. Before serving up your site, you’ll want to choose a theme! Hugo has a variety of them on [their site](https://themes.gohugo.io/.)

You will be able to filter them out based on the type of Hugo site you are interested in building up. I went with this [theme](https://themes.gohugo.io/minimal/), which is the theme you are currently seeing.

The cool thing is that all of the themes were built by someone and they sit in a github repo, so if you have any suggestions or problems you can create a **Github Issue** within that repo for some attention. Also, each theme has instructions for the most part, but if it doesn’t you can follow this [link](https://gohugo.io/getting-started/quick-start/) again and it’ll show the commands needed to place the theme within your Hugo site directory as well demoing how to update the config file to match your site info!

## Hugo Directory: Bring It Together

Once I added the theme into the theme folder, my folder setup looked like the image on the below.

![](/images/blog/hugo_vscode.png)

As you can see, I have my root files that Hugo made for me using the hugo `new site` command, plus a themes folder with the theme I installed named **Minimal.** For this theme in specific, the creator instructed to copy the contents of the config.toml file (found within the themes ‘exampleSite’ folder) and paste them into my `config.toml`, which you see right under `.gitmodules`.

The `config.toml` file for contains quite important details to run your site. Things like _baseURL_, _site title_ and _theme_ are required and also this theme allows me to change the accent colors, font as well as setup up my personal social links! After this step, I created a markdown file for my first post under content and went over to terminal, ran `hugo server -D`, which gives you a localhost URL.

## Roadblock: 404 Error Page

Visited that and my site appeared perfectly, but when I clicked on Posts from the nav bar I was being sent to a **404 Page Not Found.** I inspected and the console spit out `Couldn’t find external resources`. So pretty much, it was looking for a
`/post` folder but couldn’t find it.

It took me 30 mins to realize what was up. I was googling forums trying to find an answer. So I backtracked. I went to the themes exampleSite folder and looked within their content folder to find that within the content folder it was setup like this:

```
content
|
|
|**\_post
| |
| |** getting-started.md
| |** more-markdown-posts.md
|
|
|\_**projects
|
|\_\_ project-file-here.md
```

The difference between my themes content folder setup and mine was that I didn’t create a post and projects folder and that was why I was seeing that `404 error`. I fixed that up real quick and got my post to appear!

Keep trying, you’ll get it. And seek help if you can or need.

## Hugo Repo: Created Github Repo

I then created a github repo with the same name as my local project directory and using the command line I added the repo remote, added the files, committed and pushed them up!

![](/images/blog/hugo_github.png)

From here I will add in one more post to start with and then run the hugo site build command, which will place files into a
`/public` directory. That will generate a final build of my site and then I can host that on any web server.

## Your Turn

Shout at me with any questions!
