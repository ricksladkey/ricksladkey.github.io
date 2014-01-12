## GitHub Pages Site Using Visual Studio

This site is set up as a Visual Studio solution; posts are created, edited, previewed and pushed from with Visual Studio.

This is [my](http://ricksladkey.github.io) personal [GitHub Pages](http://pages.github.com/) site, but you can fork it and use it as a starting point if this environment sounds appealing to you.

### Recommended Components

* [Visual Studio 2010+](http://www.visualstudio.com/) as an IDE
* [VsVim](https://github.com/jaredpar/VsVim) for vi-mode awesomeness
* [Markdown Mode Extension](https://github.com/NoahRic/MarkdownMode) for WYSIWYG markdown preview
* [Jekyll](https://github.com/jekyll/jekyll) to generate the site and serve it locally
* [Visual Studio Tools for Git](http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c) or [Git Source Control Provider](https://github.com/yysun/Git-Source-Control-Provider) to push updates to [GitHub](https://github.com)
* Visual Studio Web Browser or your default browser to preview the generated site

### Usage

* Select the `_posts` folder of the _site_ project in the _Solution Explorer_.
* Create a new post using `Ctrl+Shift+A`, select _Text File_, and name it 'NNNN-NN-NN-title.md'
* Use the _Show preview window_ button to show the _Markdown Preview_ tool window (dock it with _Solution Explorer_)
* Write your post in Markdown!
* Press `Ctrl+F5` to start Jekyll (via bundle) serving your site
* `Ctrl+Click` [this link](http://localhost:4000/) to open your local site a Visual Studio editor window
* or open the `site.html` file in the editor and press `Ctrl+Shift+W` to open the local site in your default browser
* Go to _Team Explorer_ -> _Changes_ or _Pending Changelist_ and commit your changes
* Go to _Team Explorer_ -> _Unsynced Commits_ or _Git Bash_ and push to _GitHub_
