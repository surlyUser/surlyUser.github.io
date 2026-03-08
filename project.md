---
layout: default
title: "Project"
date: 2026-03-06
---
[Home](./index.html) \| [Project](./project.html) \| [About](./about.html)

# Project

## GitHub Pages

For the WMC course, a website is to be developed using GitHub Pages.

Typically, simple websites are built using HTML, CSS, and JavaScript.
More complex sites often incorporate databases, jQuery, React, CMS platforms, and various other tools.
In these cases, a GET request triggers the server to dynamically assemble the page from all available files and data
before displaying it in the user's browser. This process takes time and can be vulnerable to security threats.

GitHub Pages, however, follows the SSG (Static Site Generator) principle.
This means a generator is used to create a static version of the site in advance.
Consequently, when a client sends a request, the pre-built, finished page is delivered immediately.
This approach is both faster and more secure than the aforementioned dynamic method.

Today, even complex and highly dynamic websites can be created this way—often referred to as the JAMstack.


### Basic Tools For Github Pages

For simpler sites and themes, the following components are primarily used:

- **Jekyll as SSG:** The default Static Site Generator for GitHub Pages (though others are supported via GitHub Actions)
- **Markdown (.md) Files:** Used for managing and structuring the actual content
- **Custom HTML & CSS:** Implemented to perform individual adjustments and override theme defaults
- **Liquid:** The templating engine used to bridge the gap between content (Markdown) and the final HTML layout


## Different Ways To Create A Site

### How To

There are several ways to build a site like this:

- **From Scratch:** Building everything yourself for maximum control
- **Theme Import:** Importing an existing theme and enhancing it with your own files
- **Forking a Theme:** "Forking" a theme repository and using it as a direct foundation for your website

### Themes

The following websites provide a wide variety of **themes**:

- **jekyllthemes.io:** Offers great filtering options for blogs, portfolios, and documentations
- **jekyllthemes.org:** One of the oldest and largest collections available
- **jamstackthemes.dev:** A modern overview of high-performance static website designs

Additionally GitHub offers [Standard-Themes](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll).

### Getting Started

Find a quick-start guide here: [Quickstart-Anleitung](https://docs.github.com/en/pages/quickstart).


## Examples

### Integrating A Theme Into Your Website

After following the instructions in the *Quickstart Guide* to create your site,
you must enter the theme of your choice into the *_config.yml* file to import it.

Additionally, further information such as *title, description, and plugins* is required.
Since these requirements vary depending on the theme, it is best to consult the specific documentation
for the theme you are using.

```yml
# Basic info
title: Title
description: My first SSG site

# Theme
# remote_theme: daattali/beautiful-jekyll
remote_theme: pages-themes/modernist@v0.2.0

# Plugins
plugins:
  - jekyll-remote-theme
```

The so-called **YAML Front Matter** is also essential.
It must be placed at the very beginning of your Markdown files and serves as a reference
to other elements, such as the HTML layout file into which the content of the Markdown file will be integrated.

```md
---
layout: default
title: "About"
date: 2026-03-06
---

# H1

## H2
```

### More Advanced Themes

Most themes are built upon the basic settings mentioned above, although *fancier* themes
often require additional structures and configurations.

The *Beautiful Jekyll* theme is a prime example of a more sophisticated approach to creating and customizing a website.
By examining its repository, you will notice a much larger number of files and folders,
which enable a more refined and targeted design out-of-the-box.

While the fundamentals remain the same, the nesting and interdependence of the files are significantly more complex.

An example of this is shown below:

```html
---
layout: page
---

<!-- content: placeholder for referenced file -->
{{ content }}

{% assign posts = paginator.posts | default: site.posts %}

<!-- and some other code... -->


```

Typical folder-structure: 

![Folder example]({{ site.baseurl }}/assets/img/folder_example.JPG)
