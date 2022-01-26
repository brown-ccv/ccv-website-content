# Our work

## Directory Structure

This directory includes all content related to our work at CCV, and it populates the corresponding section on the website.

The general structure of this folder is as follows

- our-work
    - category 
        - index.yml
        - single.md
    - index.yml

The top-level `index.yml` contains the description that is shown in the banner of the `Our Work` section.
At the moment, the categories correspond to `collaborations`, `publications`, `software` and `workshops-and-talks`

ℹ️ If a new category folder is added here, the routes and cards in the website will be generated automatically. However, the menu bar needs to be changed to include the new category. 


## Categories

The schemas for each category are defined in `../schemas/` folder. See the related documentation for more details.

### Software

This directory contains `.yml` files. Each file contains information about a software or application developed by CCV. 

### Collaborations

This directory contains `.yml` files. Each file contains information about a collaboration. Collaborations highlight information about the lab or center we collaborate with, the duration of the collaborations, and it may highlight several projects and publications