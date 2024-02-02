---
title: Project Portal Completed
author: John Gerrard Holland
people: 
  - Mary McGrath
  - Joshua Lu
  - John Gerrard Holland
  - Aisulu Omar
  - Heather Yu
  - Jordan Lawson
  - Joselynn Wallace
date: 2024-02-29
slug: project-portal-completed
team: GSDC (Graphics, Software and Data Core)
project: project-portal.yml
description: Our work on the Project Portals, websites which share local and national governments’ policy projects and help find collaborators, is wrapping up after two creative and technically challenging years. We look back at the timeline, successes and challenges.
tags:
  - typescript
  - reactjs
  - nodejs
  - web
  - government

---

# Project Portal Completed

After two full years of work on the **Project Portal** – websites which share local and national governments’ policy projects and help find collaborators – we’re today handing the project off to its new home.

[![Screenshot of the San Antonio Research Partnerships Portal](/content/images/blog/project-portal-completed/satx.png)](https://researchpartnerships.sanantonio.gov)
[![Screenshot of the North Carolina Project Portal](/content/images/blog/project-portal-completed/nc.png)](https://projectportal.nc.gov)


## Prototype at the Policy Lab

In 2019, [David Yokum](https://thepolicylab.brown.edu/about/team/david-yokum) started The Policy Lab at Brown University with the goal of bringing together “experts from government, universities, and community organizations to collaborate on research tailored to inform decisions about how to improve policies and programs across the state.”

In August 2021, The Policy Lab started work on “Research Partnerships Portal” for the City of San Antonio in Texas. From the very beginning the designer [Aidan Hudson-Lapore](https://thepolicylab.brown.edu/about/team/aidan-hudson-lapore) with developers [Kevin Wilson](https://thepolicylab.brown.edu/about/team/kevin-wilson) and [Paul Xu](https://thepolicylab.brown.edu/about/team/paul-xu) envisioned an accessible, clean, and modern design, which would be compatible with stringent governmental requirements. They chose the React-based web framework [Gatsby](https://www.gatsbyjs.com) for the site, hosted on [Netlify](https://www.netlify.com), using [Airtable](https://www.airtable.com/) as a lightweight database, and by December 2021 had a working prototype.

## CCV – from Prototype to Production

CCV started work on the Project Portals in January 2022. [Mary McGrath](https://github.com/mcmcgrath13), [Joshua Lu](https://ccv.brown.edu/people/Joshua%20Lu), [John Holland](https://ccv.brown.edu/people/John%20Gerrard%20Holland), [Aisulu Omar](https://github.com/AisOmar), [Heather Yu](https://ccv.brown.edu/people/Heather%20Yu), [Jordan Lawson](https://ccv.brown.edu/people/Jordan%20Lawson) and [Joselynn Wallace](https://ccv.brown.edu/people/Joselynn%20Wallace) were involved over the course of our two-year engagement. 

Our role was to help develop the website further:
* Build a Project Portal for the Government of North Carolina,
* Convert the prototype into a JavaScript package which could easily scale to ten sites for different local governments, with support for their individual requirements, 
* Add a Content Management System (CMS) so the site could be updated directly by governmental staff, and not just the staff of The Policy Lab, and
* Add new features, like search, images and web analytics.

Over the course of 2022 we rebuilt the sites from the ground up, using much of the code from the prototype but restructuring it into new packages:
* The Project Portal "Theme" which coded all the styling and behavior of the website, and defined an interface on the [Gatsby Data Layer](https://www.gatsbyjs.com/docs/reference/graphql-data-layer/),
* A plugin to handle loading data from Airtable, and
* A plugin to handle saving and loading data using [Netlify CMS](https://www.netlifycms.org/).

![Data Flow diagram of the portal, showing how data stored in the GitHub repository are loaded by the CMS plugin into the GatsbyJS Data Layer, from where the theme plugin builds the deployed site. This all happens using GatsbyJS, running on Netlify.](/content/images/blog/project-portal-completed/data-flow.png)
￼

At the end of 2022, after testing our new implementation, we redeployed the websites in a [“Big Bang”](https://en.wikipedia.org/wiki/Big_bang_adoption), switching from the old Airtable setup to the new Netlify CMS setup with only a few minutes of downtime.

During the course of the development, we encountered some challenges, and learned some lessons.

### Data layer model
  
Gatsby’s data layer model makes data retrieval and building a page easy if you’re writing a blog with a few front-matter fields. But if you’re building pages with many fields (like the project detail pages on the Project Portals) it can become cumbersome to manage the types and queries required for them. 

### Plugins – non-standard use-cases
  
Gatsby has a lot of plugins, but there were no ready plugins we could use to handle loading the JSON files we used for the pages without specifying their metadata in three different places. 

### `@link` didn’t work for us
  
We weren’t able to leverage the [`@link` directive](https://www.gatsbyjs.com/docs/reference/graphql-data-layer/schema-customization/#foreign-key-fields) which Gatsby offers in order to build relationships between entries in different collections – like between team members and projects pages. We had to recode these connections by hand.

### The `createPages` bug
  
The major challenge of 2022 was what we now refer to as “The `createPages` Bug”, where we could build the site fine in development mode, but as soon as we packaged the theme and tried to rebuild from a fresh node project with the theme installed as a dependency, the [`createPages`-API](https://www.gatsbyjs.com/docs/reference/config-files/gatsby-node/#createPages) would fail to find the components we needed. 
  
This was extremely hard and frustrating to debug, and we resorted to building the theme entirely from scratch, interposing a `.js` file between the `.tsx` file containing each Component and the `gatsby-node.js` file which specifies which pages are made.

### Gatsby is pretty hard to debug

We found that Gatsby hides a lot of complexity from the designer, but that means also that a lot of things happen implicitly, or by convention, and often these things aren’t clearly documented. This makes debugging problems extremely difficult when they arise.

## Ongoing Development and Support during 2023

We met with the government users – all subject matter experts but not web developers – who would be updating projects on the sites to give them an introduction to the CMS. We gave each of them around an hour’s training, which turned out to be ample, and we only heard from them later if there were bugs in the CMS itself, or if they wanted changes to features. 

Over the course of 2023 we continued to maintain and the portals – adding full text search, the ability to add a mailing-list signup, expanding the coverage of the CMS to manage every part of the site, and adding better image support.

## Future at University of North Carolina

In the Fall of 2023, David Yokum informed us that he was moving to the University of North Carolina. The next keepers of the Project Portal are the fine folks of the University of North Carolina’s [Renaissance Computing Institute (RENCI)](https://renci.org). The portals are in excellent hands.

