### Example of post
```
layout: post
title:  "Lorem"
date:   2017-06-04 00:00
category: category_name
icon: git
keywords: tag1, tag2
image: 1.png
preview: 0
```

### Category page
If you want to add a page of category you have to create folder with name of category and file `index.html`, which should contain the following:  
```
---
layout: default
title: Category1
permalink: /category1/ 
---

{% include category.html %}
```

## Features
### Categories
In blog page, we categorize posts into several categories by url, all category pages use same template html file - `_includes/category.html`. Links of category in menu is in `_data.links.yml`.

For example: URL is `localhost:4000/category1`. In `_data.links.yml` we define this category named category1, so in `_includes/category.html` we get this URL(/category1/) and change it to my category(category1), then this page are posts about category1.

### Comments
I use [HyperComments](http://hypercomments.com) instead of other tool, Disqus, so it's slower and don't allows to anonymously send messages. Code of comment is in `_includes/comments` and it included in every post.

### Icons
For categories I use svg-icons in `images`. Еhe icon is automatically assigned to the post by its category. The icon name must be `category_name.svg`.

### Post Image
All images used in posts that are in `post-image` and its are categorized. For example, images in post of category1's category is in `post-img/category1`. 

### Featured image
You can specify the preview image for post in [YAML Front Matter](http://jekyllrb.com/docs/frontmatter/). In front matter called "image" to indicate the name of the image. The picture must be located in a category folder.    
For example, we write post of category_name's category. In folder `post-img/category_name` put the preview image with the title "1.png" and in front matter write: `image: 1.png`.

Also, in front matter you can control the announcement of record post. By default, the announcement consists of 35 words. Writing in the front matter called "preview" the number 0, the announcement will not be displayed for this entry. 
### Edit link
All posts can be edited by users through link: `github.com/kaptn3/future-imperfect/edit/master/{{ page.path }}` or `github.com/kaptn3/blog/edit/master/{{ post.path }}`. 

### Web analytics
I use [Yandex Metrika](https://metrika.yandex.ru) to do web analytics, you can choose either to realize it, just paste your code in `includes/analytics.html`.

## Upgrading Theme
Blog is always being improved by its users, so sometimes one may need to upgrade.

Ensure there's an upstream remote

If `git remote -v` doesn't have an upstream listed, you can do the following to add it:

`git remote add upstream https://github.com/kaptn3/future-imperfect.git`
Pull in the latest changes

`git pull upstream master`
There may be merge conflicts, so be sure to fix the files that git lists if they occur. That's it!

## Thanks to the following
[Kapitonenko](https://kaptn.ru)
[Jekyll](http://jekyllrb.com/)  
[HTML5Up](https://html5up.net/)  
[Font Awesome](http://fontawesome.io/icons/)  
[HyperComments](http://hypercomments.com)

## Copyright and license
The theme is taken Future Imperfect Theme from [HTML5 UP](https://html5up.net).

It is under [the MIT license](/LICENSE).
