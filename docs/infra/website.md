Website (fossrit.github.io)
===========================

This page documents the official FOSS@MAGIC website hosted on GitHub Pages.
The website source code is found in [FOSSRIT/fossrit.github.io](https://github.com/FOSSRIT/fossrit.github.io "Official website for Free and Open Source Software @ RIT MAGIC Center and FOSS academia").


## About

* The site is built using [Jekyll](https://jekyllrb.com/), [Bootstrap](https://getbootstrap.com/) (via CDN), [Font Awesome](https://fontawesome.com/) (via CDN), & [GitHub Pages](https://help.github.com/categories/github-pages-basics/)
* [PDF.js](https://mozilla.github.io/pdf.js/) is used for embedding PDFs in pages (via CDN)
* "Pretty links" is turned on in the Jekyll configuration (see [`permalink: pretty`](https://github.com/FOSSRIT/fossrit.github.io/blob/master/_config.yml))
* `github-pages` Gem used to simplify dependencies
* The live site is updated by committing changes to the `master` branch

_The site uses an undocumented feature of Jekyll where categories are defined using `category/_posts/` instead of `_posts/category/`._

### Git work flow

This describes how to make any type of contribution to the FOSS@MAGIC website:

1. Fork repository to your GitHub account (go to [FOSSRIT/fossrit.github.io](https://github.com/FOSSRIT/fossrit.github.io) and click "fork")
2. Clone repository locally to your workstation
3. Create/add files
4. Git commit
5. Git push to your fork
6. Open pull request against `master` branch of FOSSRIT/fossrit.github.io repository
7. When pull request is merged, site updates in a couple of minutes

### Jekyll and Front Matter

Jekyll is what builds the site.
It renders Markdown and handles templating.
_Jekyll requires that all post pages start with a valid date in the syntax `YYYY-MM-DD-<title>.md`_.

Jekyll uses something called [Front Matter](https://jekyllrb.com/docs/front-matter/) to know more information about the page.
Front Matter defines what the page looks like and metadata such as the title, author, and event details (where applicable).

Frontmatter should be at the top of a post and should be surrounded by triple-dashes (`---`).
_All times are of the timezone `America_New_York`._

Additionally, Jekyll uses the string `<!--more-->` to define where the summary of pages end.
This is used when showing post previews on the site.
Optionally, the `excerpt` frontmatter can be defined instead to override this (if using an HTML page instead of Markdown in special cases, the `excerpt` frontmatter _should be used_ instead of `<!--more-->`).
Please use this functionality to keep lists of posts readable.

#### Example post

```yaml
---
title: Example thing
layout: post
---
Hello FOSS folks!

This week...

<!--more-->

Other things happening.

- Signature
```


## Create a development environment

This website uses [**containers**](https://web.archive.org/web/20200203111523/https://www.docker.com/resources/what-container) for a development environment.
A container runtime like Docker or Podman works on Linux, macOS, and Windows.
Containers closely mimic how the production version of the site is deployed.
This means when you test your changes locally with containers, they will deploy in production successfully.
This is also how maintainers test new pull requests.

### Pre-requisites

Install one of the following container runtimes:

#### Docker

* Linux
  * [Fedora](https://developer.fedoraproject.org/tools/docker/docker-installation.html)
  * [Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
* [macOS](https://docs.docker.com/docker-for-mac/install/)
<!-- * [Windows](https://docs.docker.com/toolbox/overview/) -->

#### Podman

* [Podman installation instructions](https://podman.io/getting-started/installation)

### Build and serve Jekyll locally

To build the site and serve it as a website from your workstation, run the following script:

```sh
./build.sh
```

This script downloads the Jekyll container from Docker Hub, builds the website, and serves it on port 4000.
Make sure other services are not running on port 4000 when running the script.
Once the site finishes building, access the local version of the website at this URL:

```
http://localhost:4000
```

**PRO-TIP**: Running the script takes a while to install dependencies.
However, the container continues to rebuild the website so long as the script is still running.
To take advantage of this, run the `build.sh` script when you first start developing, and leave it running until you are done.


## How to update FOSS Hours time/place

Edit [`_config.yml`](https://github.com/FOSSRIT/fossrit.github.io/blob/master/_config.yml) and update the settings `meeting-day`, `meeting-place`, and `meeting-time`.
These settings are used across the website automatically.
The meeting time and place are referenced in the `_config.yml` so they are updated in one place.

Example:

```yaml
# --- meeting schedule settings ---

# They appear exactly as typed. Follow the format already here when updating.
meeting-day: Thursday
meeting-place: MSS/71-3190 (conference room)
meeting-time: 5:00PM - 7:00PM
```


## How to add content

This section describes how to add new content to the FOSS@MAGIC website.

Add a new `.md` file to one of the `_posts/` folders for a category.
Store assets (a.k.a. pictures, PDFs, or other downloadable files) in a folder within that category (e.g. `projects/assets/`).
Include the date in asset file names so it is clear what references it.

Content categories include the following:

* [Announcements](https://github.com/FOSSRIT/fossrit.github.io/tree/master/announcements)
* [Events](https://github.com/FOSSRIT/fossrit.github.io/tree/master/events)
* [Projects](https://github.com/FOSSRIT/fossrit.github.io/tree/master/projects)

### How to create announcements

Announcements spread the word about what is happening in the community.
Posts in this category are added to an RSS Feed (at [fossrit.github.io/feeds/latest.xml](https://fossrit.github.io/feeds/latest.xml)).

* Create a new Markdown file in `announcements/_posts/` named with the convention `YYYY-MM-DD-<title>.md`

#### Example announcement

See [2019-12-17-spring-2020-volunteers.md](https://github.com/FOSSRIT/fossrit.github.io/blob/67282a55a6330a5c61397eaeac92ef9c025f0432/announcements/_posts/2019-12-17-spring-2020-volunteers.md):

```yaml
---
author: Justin W. Flory
title: "Call for Volunteers: Spring 2020"
layout: post
---

Hi FOSS folks!
We are looking for volunteers from the RIT community!
If you are interested in volunteering with FOSS@MAGIC in the Spring 2020 semester…
```

### How to create events

Events are written before or after an event.

Events often use an image gallery functionality.
Typically, photos are added to the gallery after an event.
Use the `images` Front Matter with an array of photos.
The `images` parameter takes relative links to the RITlug site or absolute links for images hosted on other sites.
See the example event below for how to do this.

* Create a Markdown file in `events/_posts/` named with the convention `YYYY-MM-DD-<title>.md`

#### Example event

See [2019-11-05-election-night-hackathon.md](https://github.com/FOSSRIT/fossrit.github.io/blob/67282a55a6330a5c61397eaeac92ef9c025f0432/events/_posts/2019-11-05-election-night-hackathon.md):

```yaml
---
layout: event
title: Election Night Hackathon 2019
authors:
- Justin W. Flory
- D. Joe Anderson
excerpt: Help transcribe suffragist papers or hack on other project during Election Night.
images:
- /events/assets/2019/11/election1.jpg
- /events/assets/2019/11/election2.jpg
- /events/assets/2019/11/election3.jpg
- /events/assets/2019/11/election4.jpg
---
Students and faculty collaborated and worked on projects during the 2019 US midterm elections.

{% include content-blocks/gallery.html %}

> FOSS@MAGIC proudly presents… the 9th Annual Election Night Hackathon!
```

### How to add projects

Projects are about things the FOSS@RIT community work on.
They are not added to an RSS Feed.

* Create a Markdown file in `projects/_posts/` named with the convention `YYYY-MM-DD-<title>.md`
  * The date is required because of a Jekyll requirement to list projects
  * Should be updated at least once a year if project is on-going

Like events, projects often use the image gallery.

Some projects use custom HTML (in-line or entirely) to have a better show effect.
If using custom HTML, rememberto set the `excerpt` Front Matter.
If doing the page entirely in custom HTML, the `layout` should be set to `default`, which includes the FOSSRIT navbar & footer, but not the page background.

The `author`/`authors` frontmatter should be defined.
Additionally, the `permalink` property is commonly used to give a more special URL.

#### Example project

See [2018-01-01-teleirc.md](https://github.com/FOSSRIT/fossrit.github.io/blob/67282a55a6330a5c61397eaeac92ef9c025f0432/projects/_posts/2018-01-01-teleirc.md):

```
---
layout: project
title: TeleIRC
permalink: /projects/teleirc
authors:
- Mark Repka (@repkam09, original author)
- Justin W. Flory (@jwf, current maintainer)
- Seth Hendrick (@xforever1313)
- Nate Levesque (@thenaterhood)
- and others
excerpt: TeleIRC bridges Telegram groups and IRC channels.
---

{% include content-blocks/gallery.html %}

NodeJS implementation of Telegram <=> IRC bridge…
```
