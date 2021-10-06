# CCV Website Content

- home
    - banners
        - single.md
- about - markdown/yml files uniquely handled
    single.yml/single.md
- services - markdown/yml files handled consistently within a category
    - category (rates can be a category)
        - single.md
- our-work - yml files handled consistently within a category
    - category
        - single.md
- help - yml files handled consistently within a category
    - single.yml
- meta - yml files describing the above categories.
    - main - provides content to banners
        - single.yml
    - category - provides content to overview cards
        - single.yml


## Validation

We use [Yamale]() in conjuction with GitHub Actions to make sure that the content of files adheres to a specific schema.
 