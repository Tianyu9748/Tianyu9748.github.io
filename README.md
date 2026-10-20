# Tianyu Wang's personal website

A personal academic website built with [Academic Pages](https://github.com/academicpages/academicpages.github.io).

## Local preview

With Ruby 3.3 and Bundler installed:

```text
bundle install
bundle exec jekyll serve --config _config.yml,_config_local.yml --host 127.0.0.1
```

Open `http://127.0.0.1:4000`. Restart Jekyll after editing `_config.yml`.

This local copy also has a built `_site` directory. To view that without running Ruby, run the following from this folder, then open the same address:

```powershell
python -m http.server 4000 --bind 127.0.0.1 --directory .\_site
```

After editing, refresh that local build with `bundle exec jekyll build --config _config.yml,_config_local.yml`. The local configuration keeps navigation and assets on the preview server rather than the public website.

## Editing

| Content | File |
| --- | --- |
| Name, contact links, portrait, site URL | `_config.yml` |
| Introduction and industry experience | `_pages/about.md` |
| Research descriptions, sections, and display order | `_data/projects.json` |
| Publication titles, venues, paper/code links | `_data/papers.json` |
| Publication layout shared by About and Publications | `_includes/publication-list.html` |
| Downloadable CV | `assets/pdf/CV_Tianyu_Wang.pdf` |
| Navigation | `_data/navigation.yml` |
| Custom appearance | `_sass/_personal.scss` |

The profile photo is `images/tianyu-wang.jpg`; update `author.avatar` in `_config.yml` to replace it. The initials icon is retained as the favicon. Empty paper, code, and social-profile links stay hidden.

About presents the introduction, industry experience, and publications. The Publications navigation link jumps to the list on About; `/publications/` remains available as a standalone page. Research lists the four selected projects first, then additional projects, following their order in `_data/projects.json`.

The CV menu and introduction link open `assets/pdf/CV_Tianyu_Wang.pdf`; the old `/cv/` address redirects to the same file. This public copy omits the phone number and uses clickable Email, Homepage, LinkedIn, and Google Scholar icons and labels.

The updated editable master is `CV_Tianyu_Wang_public.docx` in the parent folder. For future CV changes, edit that file, export it to PDF, replace `assets/pdf/CV_Tianyu_Wang.pdf`, and rebuild the website. The editable Word file and the original private CV are not included in the site. The template's sample `files/` directory remains excluded.

## Publishing

The website is configured for [Tianyu9748](https://github.com/Tianyu9748) at **https://tianyu9748.github.io**, with source in `Tianyu9748/Tianyu9748.github.io`.

1. Edit the website and review the local preview.
2. Commit and push the changes to the repository's `main` branch.
3. In GitHub **Settings > Pages**, use **GitHub Actions**.
4. Run **Actions > Publish personal website > Run workflow** on `main`. Deployment is manual; pushing changes alone does not publish them.

The local `origin` remote is the personal website repository; `upstream` is the Academic Pages template. Review research descriptions, employer-related results, and under-review manuscript details before making future changes public.

The workflow reads the Pages origin and base path, so project-site deployments also work. To use a custom domain, configure it in GitHub Pages and update `_config.yml`.

Before publishing, useful additions are a headshot, an ORCID link, paper or preprint URLs, and project repositories. Review the downloadable CV and research details before public release. No GitHub password or token belongs in this repository.

## Credits

Academic Pages is based on Minimal Mistakes. The upstream MIT license and theme attribution are retained.
