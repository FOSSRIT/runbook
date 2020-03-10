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
Optionally, the `excerpt` Front Matter can be defined instead to override this (if using an HTML page instead of Markdown in special cases, the `excerpt` Front Matter _should be used_ instead of `<!--more-->`).
Please use this functionality to keep lists of posts readable.

#### Calendar feed

Jekyll also generates an iCal calendar feed of event announcements, talks, and events.
This feed is generated at [fossrit.github.io/feeds/calendar.ics](https://fossrit.github.io/feeds/calendar.ics).

Here is the logic for common, notable event properties:

* Titles come from the `title` Front Matter
* Descriptions come from the page body.
  Uses summaries if defined with `<!--more-->` (or `excerpt` Front Matter).
* Dates:
    * If specified, `date-start` and `date-end` allows manual specification of event date and time
        * Useful when announcement of an event is not same day as event itself
        * Also allows specifying start/end times
    * Otherwise, the date given in the file name is used
* Locations can be (optionally) specified with the `location` Front Matter
* URLs:
    * If `redirect`, gives link directly
    * If for post, gives post link
    * Otherwise, gives the [_Get Involved_](https://fossrit.github.io/get-involved/) page by default


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

### How to create event profiles

Events are written before or after an event.

Events often use an image gallery functionality.
Typically, photos are added to the gallery after an event.
Use the `images` Front Matter with an array of photos.
The `images` parameter takes relative links to the RITlug site or absolute links for images hosted on other sites.
See the example event below for how to do this.

* Create a Markdown file in `events/_posts/` named with the convention `YYYY-MM-DD-<title>.md`

#### Example event profile

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
If using custom HTML, remember to set the `excerpt` Front Matter.
If doing the page entirely in custom HTML, the `layout` should be set to `default`, which includes the FOSSRIT navbar & footer, but not the page background.

The `author`/`authors` Front Matter should be defined.
Additionally, the `permalink` property is commonly used to give a more special URL.

#### Example project

See [2020-03-01-teleirc.md](https://github.com/FOSSRIT/fossrit.github.io/blob/6d11475b205bbb564cb5b284b390b4810bec5d9b/projects/_posts/2020-03-01-teleirc.md):

```yaml
---
layout: project
title: TeleIRC
permalink: /projects/teleirc
authors:
- Justin W. Flory
- Kennedy Kong
- Kevin Assogba
- Mark Repka
- Nate Levesque
- Nicholas Jones
- Seth Hendrick
- Tim Zabel
excerpt: >
    TeleIRC bridges communication between Telegram groups and IRC channels.
    This bot was originally written for the RIT Linux Users Group Telegram group and IRC channel.
    Today, it is used by communities all over the world.
images:
- https://ritlug.com/projects/assets/teleirc/logo.svg
---

RITlug TeleIRC is a NodeJS implementation of a Telegram <=> IRC bridge.

{% include content-blocks/gallery.html %}
```

### How to add calendar events

The website has an [interactive calendar](https://fossrit.github.io/calendar/) built in.

Sometimes you want to add an event to the calendar but the details are not yet decided.
For example, weekly FOSS Hours meetings have a set time and date but typically does not have pictures or a lot of details, since it is an informal gathering.
**Calendar events** are less formal and do not require as much detail, but they show up on the _Calendar_ page.

This is different from event profiles.
Event profiles are typically showcases of significant events involving the FOSS@RIT community.

#### How to add calendar events

Create a Markdown file in the `meetings-meetups/_posts/` folder with the file name convention `YYYY-MM-DD-your-title.md` (such as `2020-04-25-imaginerit.md`).
Additionally, calendar placeholders are highly encouraged to use the `redirect` layout and Front Matter to specify a link for the event.

For example:

```yaml
---
layout: redirect
redirect: https://www.rit.edu/imagine/
date-start: "2020-04-25 10:00"
date-end: "2020-04-25 17:00"
location: "MAGIC Spell Studios"
title: "Imagine RIT"
---

Come visit the FOSS@MAGIC booth at the annual Imagine RIT festival!
Stay tuned for more info closer to the event.
```

#### How to add recurring calendar events

Calendar events can also take a `rrule` Front Matter for recurring events, written to the [iCal spec](https://icalendar.org/iCalendar-RFC-5545/3-3-10-recurrence-rule.html).

Of particular note:

> The `UNTIL` rule part defines a `DATE` or `DATE-TIME` value that bounds the recurrence rule in an inclusive manner.
> If the value specified by `UNTIL` is synchronized with the specified recurrence, this `DATE` or `DATE-TIME` becomes the last instance of the recurrence.
> The value of the `UNTIL` rule part _MUST_ have the same value type as the `DTSTART` property.

For example:

```yaml
---
layout: redirect
redirect: https://fossrit.github.io/about/
date-start: "2020-01-16 17:00"
date-end: "2020-01-16 19:00"
location: "MAGIC Spell Studios MSS-3190"
title: "FOSS Hours"
rrule: "FREQ=WEEKLY;UNTIL=20200423T190000"
---
Come meet other students and faculty involved with FOSS efforts at RIT!
```
