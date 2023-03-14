# CCV Website Content

- **home**
- **about** - markdown/yml files uniquely handled
    - single.yml/single.md
- **banners**
    - single.yml/single.md
- **help** - yml files handled consistently within a category
    - single.yml
- **images** - jpg files within a category
    - *category*
- **meta** - yml files describing the above categories.
    - *main* - provides content to banners
        - single.yml
    - *category* - provides content to overview cards
        - single.yml
- **our-work** - yml files handled consistently within a category
    - *category* - provide content to 
        - single.yml
- **schemas** - schemas for yml validation via Yamale
    - meta*.yml - validation for meta/* folders
    - single.yml - validation for folder with matching name
- **services** - markdown/yml files handled consistently within a category
    - *category* (rates can be a category)
        - single.md


## Validation

We use [Yamale]() together with GitHub Actions to make sure that the content of files adheres to a specific schema.

All schemas are defined in the `schemas` folder. When you open a Pull Request, the necessary validations are run. 
However, if you would like to validate the yml file locally you can install Yamale

To install Yamale, you can use pipx (or pip)

```
pipx install yamale
```

Then specify the schema and content folder (or file) to verify. For instance,

```
yamale -s schemas/software.yml our-work/software
```

## Icons

When icons are necessary, please refer to [these icons](https://pictogrammers.github.io/@mdi/font/5.9.55/). Note that the version linked here may have changed from that one included in the website.