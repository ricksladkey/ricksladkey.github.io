## Personal GitHub Pages Site

This site is set up as a Visual Studio solution; posts are created and previewed from with Visual Studio.

This is [my](https://github.com/ricksladkey) personal GitHub Pages site, but you can fork it and make it your own if this environment sounds appealing to you.

### Components

* Uses [Markdown Mode Extension](https://github.com/NoahRic/MarkdownMode) for WYSIWYG markdown preview
* Uses [Jekyll](https://github.com/jekyll/jekyll) to generate the site and serve it locally
* Uses [Visual Studio Tools for Git](http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c) or [Git Source Control Provider](https://github.com/yysun/Git-Source-Control-Provider) to push updates to [GitHub](https://github.com)
* Uses the Visual Studio Web Browser or your default browser to preview the generated site

### Usage

* Open the `_posts` folder of the _site_ project.
* Create a new post using `Ctrl+Shift+A`, select _Text File_, and name it 'NNNN-NN-NN-title.md'
* Use the _Show preview window_ button to show the _Markdown Preview_ tool window (dock it with _Solution Explorer_)
* Write your post in Markdown!
* Press `Ctrl+F5` to start Jekyll (via bundle) serving your site
* `Ctrl+Click` [this link](http://localhost:4000/) to open your site a Visual Studio editor window
* or open the `site.html` file in the editor and press `Ctrl+Shift+W`
* Go to _Team Explorer_ -> _Changes_ or _Pending Changelist_ and commit your changes
* Go to _Team Explorer_ -> _Unsynced Commits_ or _Git Bash_ and push to _GitHub_
