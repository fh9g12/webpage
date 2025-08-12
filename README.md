## Introduction 
A statically-generated Jekyll/Liquid/Bootstrap-based website for my academic webpage. It is based on [this repository](https://github.com/sbryngelson/academic-website-template). 

## Fork and build
If you would like to use this as a template please follow these instructions.

* Fork [this repository](https://github.com/sbryngelson/sbryngelson.github.io) by clicking the `fork` button in the top-right corner of its Github page.
* Install [Jekyll](https://jekyllrb.com/docs/installation/)  (version less than 4.0 required) on your local computer
    * On MacOS, you will need to upgrade your Ruby version from the depricated v2.3 that is shipped. Follow the above Jekyll instructions closely.
* Run `$ bundle install` to install dependenccies
* Run `$ bundle exec jekyll serve` in the repository root directory
* Your site is now hosted locally at `localhost:4000`, which you can access with your web browser.
   * It will be automatically rebuilt as you save changes to the files it contains.
   Refreshing your web browser reveals these changes.

Note:
* This webpage uses Jekyll plugins like Jekyll Scholar to automatically build your bibliography. 
  If you are using GitHub pages, you will have to build the site with the `Rakefile` in the root directory of the source branch.
  You can do so by first modifying the file as appropriate and then, after pushing your changes, execute `rake publish`.
* change the CNAME to you own custom domain or delete if not required. 

### Customization

* Modify `_config.yml` as appropriate
* Modify YAML database files, located in `_data/*.yml`, as appropriate
* Modify individual pages, located in `_pages/*.md`, as appropriate

### Navbar

The pages in the top navbar are in the `_config.yml` file.
The typical options are already included or commented on, though additional pages can be created and listed here.

### Creating or editing pages

All pages are located in the `_pages` directory.
Pages generally load information from YAML databases located as `_data/*.yml`.
Creating new pages can be done by using existing pages as a template.

#### Page header information

All pages require header information.
Example header data for the 'Talks' page is below.
```
---
title: "Talks"
layout: gridlay
sitemap: false
permalink: /talks/
---
```
The `layout` variable corresponds to HTML layouts in the `_layouts` directory.
The difference between most layouts is subtle, and `gridlay` can generally be used.
The permalink must be unique for each page and correspond to the directory storing the page in the compiled HTML.
Refer to your pages in `_config.yml` via the `title` variable.

#### Markdown

All pages are written in [Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) as `*.md`.
HTML commands and CSS styles can be directly used in a markdown files.

#### Publication page and database

The publications and talks are listed via Jekyll Scholar.
The bibliography file `lib.bib` is located in the `assets/` directory.
Modify according to your needs.

## Acknowledgment

I credit [Spencer Bryngelson](https://github.com/sbryngelson/academic-website-template) for creating the original template, who inturn credits the [Allen Lab](https://www.allanlab.org/) for creating a beautiful academic research group webpage.

## License

MIT
