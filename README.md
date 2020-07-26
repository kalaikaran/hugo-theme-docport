# Hugo docPort Theme

This repository contains a theme for [Hugo](https://gohugo.io/), based on 

* [DocDock theme](https://github.com/vjeantet/hugo-theme-docdock/).
* [Matcornic Learn theme](https://github.com/matcornic/hugo-theme-learn/).

Visit the [theme documentation](http://docport.netlify.com/) to see what is going on. It is actually built with this theme.

# Main features

- Search Engine
- Unlimited menu levels and subpages
- Placeholders to inject HTML, CSS, JS in theme without modifying it.
- RevealJS presentation from markdown (embededed or fullscreen page)
- Mermaid diagram (flowchart, sequence, gantt)
- Attachments, Icons, Buttons, Alerts, Panels, Tip/Note/Info/Warning boxes, Expand, Image resizing, shadow…, List child pages
- Excerpt ! Include segment of content from one page in another
- Customizable look and feel

![Overview](https://github.com/vjeantet/hugo-theme-docport/raw/master/images/tn.png)

## Installation

Check that your Hugo version is minimum `0.43 extended` with `hugo version`. We assume that all changes to Hugo content and customizations are going to be tracked by git (GitHub, Bitbucket etc.). Develop locally, build on remote system.

To start real work:

1. Initialize Hugo
2. Install DocPort theme
3. Configure DocPort and Hugo

### Prepare empty Hugo site

Create empty directory, which will be root of your Hugo project. Navigate there and let Hugo to create minimal required directory structure:
```
$ hugo new site .
```
AFTER that, initialize this as git directory where to track further changes
```
$ git init
```

Next, there are at least three ways to install DocPort (first recommended):

1. **As git submodule**
2. As git clone
3. As direct copy (from ZIP)

Navigate to your themes folder in your Hugo site and use perform one of following scenarios.

### 1. Install DocPort as git submodule
DocPort will be added like a dependency repo to original project. When using CI tools like Netlify, Jenkins etc., submodule method is required, or you will get `theme not found` issues. Same applies when building site on remote server trough SSH.

If submodule is no-go, use 3rd option.

On your root of Hugo execute:

```
$ git submodule add https://github.com/vjeantet/hugo-theme-docport.git themes/docport
```
Next initialize submodule for parent git repo:

```
$ git submodule init
$ git submodule update
```

Now you are ready to add content and customize looks. Do not change any file inside theme directory.

If you want to freeze changes to DocPort theme itself and use still submodules, fork private copy of DocPort and use that as submodule. When you are ready to update theme, just pull changes from origin to your private fork.

### 2. Install DocPort simply as git clone
This method results that files are checked out locally, but won't be visible from parent git repo. Probably you will build site locally with `hugo` command and use result from `public/` on your own.

```
$ git clone https://github.com/vjeantet/hugo-theme-docport.git themes/docport
```


### 3. Install DocPort from ZIP

All files from theme will be tracked inside parent repo, to update it, have to override files in theme. Download following zip and extract inside `themes/`.

```
https://github.com/vjeantet/hugo-theme-docport/archive/master.zip
```
Name of theme in next step will be `hugo-theme-docport-master`, can rename as you wish.

## Configure

Import sample config from sample site to Hugo root.

```
$ cp themes/docport/exampleSite/config.toml .
```

Change following `config.toml` line as needed, depending on method above:
```
theme = "<hugo-theme-docport-dir-name>"
```
Comment out following line, so default `themes/` will be used:

```
# themesdir = "../.."
```

#### (Bonus)
Create empty file `.gitkeep` inside `public/` and add following to `.gitignore`.  This way it will keep repo smaller and won't bring build result files and errors to remote checkout places:
```
/public/*
!/public/.gitkeep
```

### Preview site
```
$ hugo server
```
to browse site on http://localhost:1313

## Usage
- [Visit the documentation](https://docport.netlify.app/)
- [Hugo docs](https://gohugo.io/getting-started/configuration/)
- [Git submodules](https://git-scm.com/docs/git-submodule)
