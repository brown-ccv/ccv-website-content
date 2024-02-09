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

<figure>
    <a href="https://researchpartnerships.sanantonio.gov">
      <img 
        src="/content/images/blog/project-portal-completed/satx.png" 
        alt="Screenshot of the San Antonio Research Partnerships Portal" 
        width=500 
        height=495 
      />
    </a
    <a href="https://projectportal.nc.gov">
      <img 
        src="/content/images/blog/project-portal-completed/nc.png" 
        alt="Screenshot of the North Carolina Project Portal" 
        width=500 
        height=495 
      />
    </a>
  <figcaption>
    Screenshots of the Project Portals in February 2024
  </figcaption>
</figure>

## Prototype at the Policy Lab

In 2019, [David Yokum](https://thepolicylab.brown.edu/about/team/david-yokum) started The Policy Lab at Brown University with the goal of bringing together “experts from government, universities, and community organizations to collaborate on research tailored to inform decisions about how to improve policies and programs across the state.”

In August 2021, The Policy Lab started work on [“Research Partnerships Portal” for the City of San Antonio in Texas](https://researchpartnerships.sanantonio.gov). From the very beginning the designer [Aidan Hudson-Lapore](https://thepolicylab.brown.edu/about/team/aidan-hudson-lapore) with developers [Kevin Wilson](https://thepolicylab.brown.edu/about/team/kevin-wilson) and [Paul Xu](https://thepolicylab.brown.edu/about/team/paul-xu) envisioned an accessible, clean, and modern design, which would be compatible with stringent governmental requirements. They chose the React-based web framework [Gatsby](https://www.gatsbyjs.com) for the site, hosted on [Netlify](https://www.netlify.com), using [Airtable](https://www.airtable.com/) as a lightweight database, and by December 2021 had a working prototype.

## CCV – from Prototype to Production

CCV started work on the Project Portals in January 2022. [Mary McGrath](https://github.com/mcmcgrath13), [Joshua Lu](https://ccv.brown.edu/people/Joshua%20Lu), [John Holland](https://ccv.brown.edu/people/John%20Gerrard%20Holland), [Aisulu Omar](https://github.com/AisOmar), [Heather Yu](https://ccv.brown.edu/people/Heather%20Yu), [Jordan Lawson](https://ccv.brown.edu/people/Jordan%20Lawson) and [Joselynn Wallace](https://ccv.brown.edu/people/Joselynn%20Wallace) were involved over the course of our two-year engagement. 

Our role was to help develop the website further:
* Build a [Project Portal for the Government of North Carolina](https://projectportal.nc.gov),
* Convert the prototype into a JavaScript package which could easily scale to ten sites for different local governments, with support for their individual requirements, 
* Add a Content Management System (CMS) so the site could be updated directly by governmental staff, and not just the staff of The Policy Lab, and
* Add new features, like search, images and web analytics.

The prototype was set up as a single repository containing the data for both the San Antonio and North Carolina portals, each in its own directory. We used different commands: `npm build:satx` and `npm build:nc` commands to build each version of the site. 

The benefits were compelling:
* **All the code in one place**: A single repository makes it trivial to download and install the code for any and all of the sites. Deploying all the sites needed only a single interaction – triggering the GitHub Actions deployment script on the single repo.
* **Low-effort changes** Any changes made on one site would automatically be reflected on all the others.

The drawbacks were major:
* **Tight coupling**: By having all the code in a single repository and having all the sites deploy immediately whenever we merged code into the [main branch](https://www.atlassian.com/continuous-delivery/continuous-integration/trunk-based-development), we risked outages if, inevitably, a faulty bit of code made it through our pull request review process.
* **Separation of concerns**: The single repository would get more and more unwieldy as new jurisdictions were added, and if one of them had totally different requirements (like having to be hosted on a different service) then we would have to fork the repository and maintain duplicate codebases. 
* **Too coarse permissions**: The content management system would give the government staff managing each site permissions to modify the common git repository. If the single repository approach was kept, there was a chance that a modification by staff for one site might inadvertently break something for _all_ the sites in that same repository.

Instead, we decided to split the code across several repositories:
* A monorepo with the "business logic." We would publish packages of this code, and those packages would be installed independently.
* Independent repositories for each of the sites.

Over the course of 2022 we rebuilt the sites from the ground up, restructuring the code from the prototype and adding new functionality. We published three new packages:
* The Project Portal "Theme" which coded all the styling and behavior of the website, and defined an interface on the [Gatsby Data Layer](https://www.gatsbyjs.com/docs/reference/graphql-data-layer/),
* A data plugin to handle loading data from Airtable, and
* An alternative data plugin to handle saving and loading data using [Netlify CMS](https://www.netlifycms.org/), which saves its data into the git repository from which the site is built.

We had planned to transition the sites to using the new packages step by step: 1) migrate from a single repo to multiple repositories but keep Airtable for data storage, then 2) switch from the Airtable plugin to the Netlify CMS plugin. 

However, after testing our new implementation, we decided it was easier and less risky to migrate the websites in a [“Big Bang”](https://en.wikipedia.org/wiki/Big_bang_adoption), switching from the old single-repo with Airtable setup to the new multi-repo with Netlify CMS setup. The Airtable plugin was never used in production.

The final structure of the site's data flow is shown in the figure below.

<figure>
  <img 
    src="/content/images/blog/project-portal-completed/data-flow.png" 
    alt="Data Flow diagram of the portal, showing how data stored in the GitHub repository are loaded by the CMS plugin into the GatsbyJS Data Layer, from where the theme plugin builds the deployed site. This all happens using GatsbyJS, running on Netlify." 
    width=1368 
    height=488
  />
  <figcaption>
    Data flow of the portal from storage on GitHub to the deployed site.
  </figcaption>
</figure>


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

