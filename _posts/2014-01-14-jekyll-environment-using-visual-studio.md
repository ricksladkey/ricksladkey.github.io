---
layout: post
title:  "GitHub Pages Jekyll Environment using Visual Studio"
date:   2014-01-14 01:00:00
categories: jekyll visualstudio
---

I cobbled together a hacker-friendly environment for this blog as a Visual Studio project; posts are created, edited, previewed and pushed from with Visual Studio.

The [GitHub repository](https://github.com/ricksladkey/ricksladkey.github.io) for [this site](http://ricksladkey.github.io) is a template for a personal [GitHub Pages](http://pages.github.com/) site, but you can fork it and use it as a starting point if this environment sounds appealing to you.

### Recommended Components

* [Visual Studio 2010+](http://www.visualstudio.com/) as an IDE
* [VsVim](https://github.com/jaredpar/VsVim) for vi-mode awesomeness
* [Markdown Mode Extension](https://github.com/NoahRic/MarkdownMode) for WYSIWYG markdown preview
* [Jekyll](https://github.com/jekyll/jekyll) to generate the site and serve it locally
* [Bundler](https://github.com/bundler/bundler/) to keep your Ruby gems in sync with GitHub
* [Visual Studio Tools for Git](http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c) _or_ [Git Source Control Provider](https://github.com/yysun/Git-Source-Control-Provider) to push updates to [GitHub](https://github.com)
* [GitDiffMargin](https://github.com/laurentkempe/GitDiffMargin) for keeping track of changes
* Visual Studio Web Browser or your default browser to preview the generated site

### Usage

* Open the `site.sln` in Visual Studio
* Select the `_posts` folder of the `site` project in the _Solution Explorer_.
* Create a new post using `Ctrl+Shift+A`, select _Text File_, and name it `NNNN-NN-NN-title.md`
* Use the _Show preview window_ button to show the _Markdown Preview_ tool window (dock it with _Solution Explorer_)
* Write your post in Markdown!
* Press `Ctrl+F5` to start Jekyll (via bundle) serving your site
* `Ctrl+Click` [this link](http://localhost:4000/) to open your local site a Visual Studio editor window _or_
* open the `site.html` file in the editor and press `Ctrl+Shift+W` to open the local site in your default browser
* Continue with "edit, preview" cycle until you are happy with the results
* Go to _Team Explorer_ -> _Changes_ or _Pending Changelist_ and commit your changes
* Go to _Team Explorer_ -> _Unsynced Commits_ or _Git Bash_ and push to _GitHub_
