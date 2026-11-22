# akshaim.github.io

Personal site of Akshai Murukakumar, published with GitHub Pages from the `master` branch at <https://akshaim.github.io/>.

It is plain HTML with one stylesheet. There is no build step and nothing to install.

## Layout

| Path | What it is |
|---|---|
| `index.html` | Profile page |
| `assets/site.css` | The only stylesheet for the profile and the notes |
| `4DIAC/`, `IoT/`, `Fablab/` | Notes and tutorials from 2015–2017, kept as an archive at their original URLs |
| `MicroHOPE/Controllers - AVR/` | reveal.js slide deck |
| `academic/` | Paper summary with its LaTeX source |
| `zve_calc/`, `Buy_vs_Rent/`, `Rental_Real_Estate_Wealth_Calculator/` | Independent single-file tools. They do not use the site stylesheet and are not linked from the profile. |
| `robots.txt`, `sitemap.xml`, `404.html`, `.nojekyll` | Site plumbing |

## Preview locally

```sh
python3 -m http.server 8000
```

Then open <http://localhost:8000/>.

## When your role changes

The profile states each fact in three places in `index.html`. Change all three together:

1. `<title>` and the `description` and `og:` meta tags in the `<head>`
2. the JSON-LD block (`<script type="application/ld+json">`)
3. the visible text: headline, introduction and "At a glance"

Then update `dateModified` in the JSON-LD and the `<lastmod>` of the first entry in `sitemap.xml`. The page itself does not show a date.

## Adding a post to "Latest posts"

The list on the profile is written by hand; it does not update itself. After publishing a note on HackMD, add one line at the top of the list in the `posts` section of `index.html`, with the month, the title and the note's public link.

## Adding a page

Copy an existing note such as `IoT/NodeMCU/NodeMCU-101.html`. Keep its `<head>`, header and footer, replace the content inside `<main>`, link the new page from `index.html`, and add it to `sitemap.xml`.

## To do

- **Update "Latest posts" automatically.** Today the list is edited by hand. Planned: a GitHub Actions workflow that reads the public HackMD profile, rewrites the list in `index.html` and commits it. It should run weekly, keep its own schedule alive (GitHub pauses scheduled workflows after 60 days without repository activity), offer a "Run workflow" button for an immediate refresh, and list only notes carrying a chosen tag so that personal notes never appear.

## License

Content is available under [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/). The slide deck uses reveal.js (MIT; see the `LICENSE` file in its folder).
