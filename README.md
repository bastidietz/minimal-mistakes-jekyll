# Minimal Mistakes Jekyll
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/limyunkai19/minimal-mistakes-jekyll/blob/master/LICENSE)

Ready to use Jekyll template with Minimal Mistakes theme. Instant blog without knowing git and command line. Just fork it to use for your GitHub Pages.

Demo: <https://limyunkai19.github.io/minimal-mistakes-jekyll/>

## Getting Started
I am writing this README for non-technical people who intended to blog using Jekyll on GitHub Pages too. Hence, some part might be too trivial for those who know GitHub well, feel free to skip those.

### Installation for Your GitHub Pages
[Fork](https://help.github.com/articles/fork-a-repo/#fork-an-example-repository) Minimal Mistakes Jekyll to your own Repository.

Publish the site with GitHub Pages on:
- <https://username.github.io> (recommended)
    + rename the forked repository to username.github.io
    + your site should be available at <https://username.github.io> after renaming


- <https://username.github.io/repositoryname>
    + rename the forked repository to a name you like, for example my-awesome-blog
    + go to setting, publish your `master` branch with GitHub Pages, detail steps at [here](https://help.github.com/articles/configuring-a-publishing-source-for-github-pages/#enabling-github-pages-to-publish-your-site-from-master-or-gh-pages)
    + your site should be available at <https://username.github.io/my-awesome-blog>

After the sites had been published continue to [Usage section](#usage) section to add content to your site.

### Installation for Local Development (optional)
This section is for those who wish to develop their site locally and use git to commit changes for the site. It assumes the knowledge of command line. You may [skip](#file-structure) this section if you don't know git or don't want to touch the command line.

**Prerequisites**

- Git
- [Jekyll](https://jekyllrb.com/docs/installation/) and [Bundle](http://bundler.io/#getting-started)

**Installation**

Make sure all prerequisites are installed and you had forked the repository.

Run the following command in your terminal:

```sh
# Clone your forked repository
git clone https://github.com/username/minimal-mistakes-jekyll.git

# Change directory
cd minimal-mistakes-jekyll

# Build the site using Jekyll and serve the site
bundle exec jekyll serve
```

Your site should be available at <http://localhost:4000>.

Develop your site, commit new changes and push to GitHub master branch, any new changes will be reflected on GitHub Pages in a few seconds after you push the commits.

## File Structure
This section explains the file structure in a Jekyll site. It is optional but recommended to understand Jekyll.

Jekyll is a static site generator, it generates a static website based on the given content. Hence, the following files tell Jekyll how to generate your site and determine how your site will look like.

Generally the files and directories in a Jekyll sites can be classify into 4 types.

1. Theme files and directories. <a id="theme"></a> These files specify how your sites looks like. In this repo, these files are copied directly from Miminal Mistakes [repository](https://github.com/mmistakes/minimal-mistakes). They are:
   - `_includes`
   - `_layouts` (HTML templates)
   - `_sass` (CSS styles)
   - `assets`

2. Jekyll files and directories. These files are essential for Jekyll to generate your sites. They are:
   - `_config.yml` the global configuration of your site, see [Usage section](#usage)
   - `index.html` the 'home' pages, and yes it is blank

3. Content files and directories. These files determines the content of your site. You should focus and mainly make changes on these files. They are:
   - `_posts/` (contains your blog post)
   - `_pages/` (contains the static page)
   - `_drafts/` (contains unpublished draft)
   - `_data/navigation.yml` (your site navigation)
   - `assets/images` (your site images or other files)

4. Others. Such as:
   - `.gitignore` (Git stuff)
   - `Gemfile` (Ruby stuff)
   - `Gemfile.lock` (Ruby stuff)
   - `LICENSE` (License)
   - `README.md` (This readme)

## Usage
### Site Configuration
First you will need to configure your site settings. This can be done by editing the `_config.yml` file. Following are those lines that you should changes and those lines that you can change.

**Settings that you should change:**

Line number | Setting   | Explanation
------------|-----------|------------
12          | title     | Your site title
14          | name      | Your name
15          | description| A short description about your site
85 - 115    | author    | Your details

**Settings that you can change:**

Line number | Setting   | Explanation
------------|-----------|------------
8           | minimal_mistakes_skin | Change your skin, refer to [minimal mistakes skin](https://github.com/mmistakes/minimal-mistakes#skins-color-variations)
54          | search    | Set it to `true` to add search function
182         | permalink | Change your permalink, refer to Jekyll [documentation](https://jekyllrb.com/docs/permalinks/)


### Write Blog Posts
Navigate to the `_posts` directory in github.com, for example `https://github.com/username/repositoryname/tree/master/_posts`.

Click on create new file and follow the [naming convention](https://github.com/limyunkai19/minimal-mistakes-jekyll/blob/master/_posts/2017-12-21-welcome-to-minimal-mistakes-jekyll.md).

You will need a [YAML front matter](https://jekyllrb.com/docs/frontmatter/) for every beginning of your post. Basically the following:
```
---
title:  "Welcome to Minimal Mistakes Jekyll"
date:   2017-12-21
categories: update
tags: jekyll
---
```
Change the title and date, categories and tags are optional. Note that the 3 dashes above and 3 dashes below are important.

After the YAML front matter (after the 3 dashes) you may start writing your own post in markdown. You may find this [cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) handy.

Then, click on preview to check if your markdown is correct and the rendered content is what you want (you may ignore the first table, it will disappear in your published site).

After everything is okay, commit this file and wait around 10 seconds for GitHub Pages to reflect your changes.

**Note:** you may refer to the [source code](https://raw.githubusercontent.com/limyunkai19/minimal-mistakes-jekyll/master/_posts/2017-12-21-welcome-to-minimal-mistakes-jekyll.md) of the example blog post and its [rendered result](https://limyunkai19.github.io/minimal-mistakes-jekyll/update/welcome-to-minimal-mistakes-jekyll/) to understand more about how to write a blog post 

### Add Pages
A page contain content that usually permanent, like about page. You may add other pages, for example, experience, resume or CV. You may also remove pages like the **Source Code** on the top right corner.

Adding a page is similar to adding a blog post, just a little more work to do.

First, navigate to `_pages` directory, then add new file.

As for the front matter, you will need permalink and title, refer to the following:
```
---
permalink: /about/
title: "About"
---
```
Then, similar to blog post, write the content in markdown, check using preview and commit this file.

Next, for you pages to appear in the navigation bar, you will need to edit `_data/navigation.yml`. Refer to existing `about`, you will know that you need to add in `title` and `url`. You may remove the `Source Code` from the navigation bar too by simply deleting the 2 lines related to it.

### Write Drafts
Dealing with drafts is a little inconvenient with GitHub interface but it is still possible.

Similar to adding blog post, go to `_drafts` directory and add a file for your draft.

To publish your draft, click on `raw` then copy the content, create new file in `_posts` then paste the draft content. Don't forgot about YAML front matter and naming convention.

**For local development**

Use the following command to view your drafts
```sh
bundle exec jekyll serve --drafts
```

### Add Images
To add an image to your blog post, for example `awesomeimage.jpg`.

First, upload the images to `assets/images` directory.

Then in your blog post, use the following syntax to include your image
```
![alt_text]({{ "assets/images/awesomeimage.jpg" | absolute_url }})
```
`alt_text` is the text to be displayed when your there is an error in rendering your images.

It is also possible to insert an images with link, refer to [here](https://github.com/limyunkai19/minimal-mistakes-jekyll/blob/master/_drafts/first-draft.md) for more detail.

### Use Custom Domain
First, register your domain name, say `example.com` at any DNS provider.

Before we start to setup, do note that there are [several ways](https://help.github.com/articles/quick-start-setting-up-a-custom-domain/) to setup an custom domain. We will setup our custom domain with apex domain and `www` subdomain, which mean visitor will be able to visit your site on either `www.example.com` or `example.com`.

Go to your repository settings, under `Custom domain`, type in your custom domain, `example.com` and click **save**. Refer to [here](https://help.github.com/articles/adding-or-removing-a-custom-domain-for-your-github-pages-site/) for more detail steps.

Then, at your DNS provider, create 3 DNS record for your domain:
- A record for **@** pointing to `192.30.252.153`
- A record for **@** pointing to `192.30.252.154`
- CNAME record for **www** pointing to `username.github.io.` (*mind the extra period!*)

Refer to [here](https://www.namecheap.com/support/knowledgebase/article.aspx/9645/2208/how-do-i-link-my-domain-to-github-pages) and [here](https://gist.github.com/mapsam/ce60b87eea561ea6bdbf) as well as GitHub official help ([`www`](https://help.github.com/articles/setting-up-a-www-subdomain/) and [apex](https://help.github.com/articles/setting-up-an-apex-domain/)) for more information.


## Customization
You can make changes to [Theme files](#theme) or the `_config.yml` files to customize your site styles and look. I have made the following customization based on Minimal Mistakes theme.

**Reduce font size** - this [commit](https://github.com/limyunkai19/minimal-mistakes-jekyll/commit/b8a070f069827f2701964a2322e5882123429a4f). You may change the font size to suit your needs.

**Slight redesign the sidebar and title** - this [commit](https://github.com/limyunkai19/minimal-mistakes-jekyll/commit/4de8205edda75a2fbb2ca37088405db1809f1589).

All others are left unchanged.

You can even **change the theme** to be any Jekyll theme by replacing related [Theme files](#theme) to be your destination theme. However, do note that different theme has different layout options. This template is setup to use `single` layout from the Minimal Mistakes theme as a default layout. In the case that your destination theme does not support `single` layout or you wish to change the default layout, change the default layout at [line 248](https://github.com/limyunkai19/minimal-mistakes-jekyll/blob/cb6f671e52bc6295d0ddf057e63e2f2ffea674a8/_config.yml#L248) and [line 255](https://github.com/limyunkai19/minimal-mistakes-jekyll/blob/cb6f671e52bc6295d0ddf057e63e2f2ffea674a8/_config.yml#L255) of `_config.yml` file. Sometimes, there is also a need to make changes on `_config.yml` to resolve the incompatibility between different themes.

Read the official Jekyll [documentation](https://jekyllrb.com/docs/home/) to further customize the site for your own need.


## Credits
Theme by [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) release 4.8.0
