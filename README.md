# polarhub
The Polar Hub on Jekyll

[![Build Status](https://travis-ci.org/ccnmtl/polarhub.svg?branch=master)](https://travis-ci.org/ccnmtl/polarhub)

## How to create new content
### Preliminary Info about content files and Markdown
An individual page in Jekyll is stored in an individual files (with the file extension `.md` for Markdown).  Files of content can be organized into collections in the following folders:
```
_core_projects  
_news_items  
_resources  
```
A content file can be saved in the root directory of the project, or in one of these collections. Saving to a collection lets the site "know" that it should handle a given piece of content a certain way.  For example, creating a new Markdown file in `_news_items` will have the site list that piece of content as in the news item listings page.

The first few lines of content files should consist of 'front matter'.  This is a listing of key-value pairs that provide a structured way of organizing data about a file. This front matter is listed between two lines of three dashes. For example:

```
---
title: "This is the title of my new Polarhub page"
date: 11/12/17
some_arbitrary_field: "This is arbitrary data"
---
```

Markdown is a language that makes it easier to format text for the web.  Jekyll reads in the Markdown and churns out nicely formatted HTML.  A useful cheatsheet for Markdown can be found [here](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

### Creating new content
To create new piece of content for the site, simply create a new Markdown file in the root directory or in the collection of your choice.  To ensure that the front matter for your new item is consistent with other pages its suggested that you copy the front matter from another page of the same collection.

### Front matter defaults
For reference, below are some boilerplate code you can use to start creating a new page:

__page__ (this would be a page in the root directory)

```
---
layout: page
title: "The title of the page"
permalink: /some/path.html # this is the path that you would like to page to appear
---
```

__Core Project__

```
---
layout: core_project 
title: "Online Professional Development for Teachers: Climate Change"
image: /files/W1E1_1_full.jpg
image-alt: "A glacier floating in the sea."
short-title: AMNH Climate Courses
landing-page-image: /files/project-square-opd.png
landing-page-description: "Teachers and lifelong learners dive into the science of climate change through online and in person courses."
permalink: /core-projects/amnh_climate_courses.html
---
```
* Layout: is the template that Jekyll should use to render this page. For Core Projets, always use `core_project`
* Title: self-explanitory
* Image: this is the path to the image to display on the page
* Image Alt: This is the alt text associated with the image. It is the text that is read by screen readers. As these images often convey meaningful information about the project, its best to fill these in with a description that descibes the image in the context of the project.
* Short Title: This is the title that appears on the Core Projects listing page
* Landing Page Image: is the image that appeears on the Core Projects listing page
* Landing Page Description: is the description that appears on the landing page
* Permalink: is the link where the page should render.  Core project permalinks should always start with `/core-projects/`

__News Item__

```
---
layout: news_item
title: "AMNH Connects Lifelong Learners to Climate Change"
date: "December 15, 2014"
author: "Jessica Brunacini"
description: "PoLAR stipends offer opportunities to teachers"
image: "/assets/img/news-items/AMNH_1Day_PI-StephaniePfirman.jpg"
---
```

* Layout: The layout for a news item should always be `news-item`
* Date: Jekyll supports various date formats, but for consistency its suggested to follow the format in the example
* Description: This is the text that appears on the News listing page

__Resource__

```
---
layout: resource
title: "A Coastal Arctic Food Web"
date: "September 10, 2013 - 2:42pm"
author: "University of Alaska Fairbanks"
resource_link: "http://arcticclimatemodeling.org/lessons/acmp/acmp_912_SeaIceDynamics_ACoastalAr..."
resource_type:
  - Curriculum
climate_topics:
  - Impacts of Climate Change
polar_topics:
  - Arctic
  - Sea Ice
  - Marine Ecosystem
  - Terrestrial Ecosystem
audience:
  - High School
---
```

* Layout: similar to the other collections, Resources should always use `resource` for the layout
* Author: The author of the resource
* Resource Link: the link to the resource
* Tags: Resources have four different types that you can use to classify resource content. The four tags are specified below.  Though these tags are specified, and arbitrary value can be listed for a given tag. Follow the format in the example; each line starts with two spaces, a dash, another space, and then the string to specific the tag.  As you can see in the example, you can assign multiple values to the same tag.
* `resource_type`
* `climate_topics`
* `polar_topics`
* `audience`

                        
## How to upload images

Images for content are stored in the [files folder](https://github.com/PoLAR-Hub/polarhub/tree/master/files). Click over to the files folder and simply upload the file there. Github's instructions can be found [here](https://help.github.com/articles/adding-a-file-to-a-repository/)

## How to update existing items
Existing items can be edited from Github.  Again instructions can be found [here](https://help.github.com/articles/editing-files-in-your-repository/)

## How to delete entire items
Items can be deleted following Github's [instructions](https://github.com/blog/1545-deleting-files-on-github).

## Which branch to update
Github uses the concept of branches to organize changes of code.  Though this is useful for developers, as content editors, you need not worry about this.  You can commit your changes directly to the master branch.

## General Site Configuration
This DNS for this site is configured to point to CloudFlare which then proxies back to GitHub, which actually hosts the site. This is done to provide an HTTPS support to site visitors. The CloudFlare account is on a free plan and requires little maintenance.
