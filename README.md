# Zhaoxin Meng — personal website

Personal website for Zhaoxin Meng, Industrial PhD at Einride and Doctoral Researcher at Chalmers in Gothenburg, Sweden. Built with Jekyll and compatible with native GitHub Pages hosting at [zhaoxinmeng.com](https://zhaoxinmeng.com).

## Edit content

- `_data/profile.yml`: primary content source for the home, research, and CV pages, including roles, education, publications, patents, and awards.
- `_pages/about.md`: homepage introduction and section structure.
- `_pages/publications.html`: research page.
- `_pages/cv.md`: printable CV. The **Print / Save PDF** button opens the browser print dialog; no pre-generated or missing PDF is linked.
- `_layouts/profile.html`: shared layout, navigation, and metadata.
- `assets/css/profile.css`: responsive styles, reduced-motion support, and print layout.
- `_data/cv.json`: legacy structured CV data; update alongside the primary profile if this file is consumed elsewhere.

Institutional logos are stored locally in `images/logos/` and configured in `_data/organizations.yml`; their official sources are recorded in `images/logos/SOURCES.md`. No JavaScript framework, npm build, external fonts, or remote image dependencies are needed for these pages. JavaScript only enables printing; navigation and all content work without it.

## Local development

Use a maintained Ruby installation (Ruby 3.1+ recommended) and Bundler:

```sh
bundle install
bundle exec jekyll serve --host 127.0.0.1
```

Build for deployment with `bundle exec jekyll build`. GitHub Pages can build this repository with its native Jekyll integration; the custom domain remains in `CNAME`. A repository edit does not by itself publish a deployment.

## Content provenance — September 2026

The owner supplied the latest LinkedIn profile text for this update. It is the source for the September 2026 Einride Industrial PhD and Chalmers Doctoral Researcher roles, University of Gothenburg PhD enrollment, SSF funding, HONOR Principal Engineer title and tenure, 2026 humanoid competition achievements, detailed internship dates, and education. The two current roles represent the industrial doctoral arrangement, not two separate PhD programs.

- [LinkedIn profile](https://www.linkedin.com/in/zhaoxin-meng-a0b248111/): full profile is login restricted. The public search summary still described the prior HONOR role at the time of the update; the newer owner-supplied text takes precedence.
- [MF-Net paper](https://doi.org/10.1109/IJCNN52387.2021.9534374) and [IJCNN 2021 proceedings contents](https://www.proceedings.com/content/060/060367webtoc.pdf): publication title, venue, and author list.
- [ITAIC 2019 proceedings contents](https://www.proceedings.com/content/049/049879webtoc.pdf): hippocampus segmentation paper title, authors, and venue.
- Patent titles/numbers, awards, and contact links were retained from the original personal website. Patent years were omitted because the previous page did not distinguish filing and publication dates. Links go to the matching patent records.

Upstream Academic Pages sample sources are preserved but excluded from the published site in `_config.yml`; they must not be mistaken for the owner’s work. The old `/about/`, `/resume`, and `/cv-json/` routes redirect to the updated pages. The homepage uses the owner-supplied portrait in the introduction and a separate illustrated avatar beside the name in the site header. The typographic monogram remains the favicon.

Original theme: [Academic Pages](https://github.com/academicpages/academicpages.github.io), under the repository’s MIT license.
