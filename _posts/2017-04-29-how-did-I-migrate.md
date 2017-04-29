---
layout: post
title:  "How did I migrate from Blogger to GitHub/Jekill?"
date:   2017-04-29 00:00:00
#categories: jekyll,git,github
---

### **Hi, all!**

<br>
I've just started pushing the studies harder to make my main goal of being very skilled in R programming, Python and some Data Science concepts (in a feasible way, of course) becoming reality this year.
 
So let's summarise some stuff I've learnt so far in a few paragraphs.

The main idea is migrating my blog to [GitHub Pages](https://pages.github.com) and start using Jekyll, which is an open source site generator and its best feature is being easy to manage and organise to create a simple blog or static website. So, hopefully, now this post is being read in the new URL. Yay!

I am doing a similar stuff that the [R-Ladies London Community](https://www.meetup.com/rladies-london) taught in the [last Wednesday meetup](https://www.meetup.com/rladies-london/events/239404233).

So here are a few concepts that will be useful in case you want to follow my path :)

<br>
**1. Download [Git](https://git-scm.com)**

Git is a free and open source distributed version control system designed to handle everything from small to very large projects;

<br>
**2. Create a [GitHub](https://github.com) account**

GitHub is a web-based Git or **version control repository** and Internet hosting service. It offers all of the distributed version control and source code management functionality of Git as well as adding its own features.

If you want to manage your apps/docs/anything's versions without losing control, you have to know how to work with Git Hub.
Once you create an account on the website, you can upload your files from the browser, install the GitHub software in your computer or access it from the command line.

Now, next step is installing [Jekyll](https://jekyllrb.com), but being a [Ruby Gem](https://rubygems.org), you will have to install Ruby.

<br>
**3. Install [Ruby in Windows](http://stackoverflow.com/questions/18908708/installing-ruby-gem-in-windows)**

>- Install Ruby via RubyInstaller: <http://rubyinstaller.org/downloads/>
>- Check your ruby version: Start - Run - type in cmd to open a windows console
>- Type in ruby -v*
>- You will get something like that: ruby 2.0.0p353 (2013-11-22) [i386-mingw32]
>- Download and install DevelopmentKit from the same download page as Ruby Installer. Choose an .exe file corresponding to your environment(32 bits or 64 bits and working with your version of Ruby).
>- Follow the installation instructions for DevelopmentKit described at: https://github.com/oneclick/rubyinstaller/wiki/Development-Kit.
>- Adapt it for Windows.
>- After installing DevelopmentKit you can install all needed gems by just running from the command prompt (windows console or terminal): gem install {gem name}. For example, to install rails, just run gem install rails.


**4. Install Bundler and [Jekyll](https://jekyllrb.com)**

You are going to install Bundler via Gem (Ruby package manager). Bundler manages Ruby gem dependencies, reduces Jekyll build errors, and prevents environment-related bugs
Open your windows console and type in:

```ruby
gem install bundler
```
and after that...

```ruby
gem install jekyll
```
<br>
Now, let's create a new folder in your repository using the command line to start creating your blog.
<br>

**4. Create a new folder in your [GitHub repository](https://pages.github.com)**

Head over to GitHub and create a new repository named *username.github.io*, where username is your username (or organization name) on GitHub.
**Important!! It has to be named exactly as your Github username, otherwise it won't work with Jekyll.**

Now, you have to clone your repository to your local drive.

In the command line, create a folder in your C: drive that will be easy to find, eg. "C:\git"

```
cd C:\
mkdir git
cd git
```
Now, you are going to clone your repository to your local drive, thus you will have it local and online.
Every time you will make any changes in your local folder, in order to make it public in your webpage you have to commit to GitHub.

```
git clone https://github.com/username/username.github.io
```

To sync it, you are going to type in:

```
git add --all
git commit -m "Type any comment here you want to appear in the log"
git push -u origin master
```

After creating the folder, it will be easier if you choose a template for your blog and fork the Github repository.

You can find some Jekyll templates [here](http://jekyllthemes.org).
After choosing one, you should fork the template repository by clicking on the "fork" button as you can see in the print screen below:
<br>

![alt text](\static\img\fork_gh.PNG "Fork GitHub")
<br>

Some GitHub Pages instructions might help as well: <https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages>

Yay!! You are almost done! I mean, the next step is starting modifying or creating your new blog, but at least you already have everything almost set up!

I am also using the Visual Studio Code, which is, basically, a source code editor that works with many programming languages and in most of the OS types (Windows, Mac, Linux). So it is extremly useful to code in any language and manage all the website pages you might have in your repo.

Very recommended: [Visual Studio Code](https://code.visualstudio.com)

I suppose the next steps is up to you guys.

In case of questions, please leave comments below!

Thanks and see you soon! :)
<br>
**Tip of the day:** 
I love Cheat Sheets and this Github simple functions one is short and efficient:
<https://education.github.com/git-cheat-sheet-education.pdf>


