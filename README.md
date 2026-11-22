# akshaim.github.io

Personal site of Akshai Murukakumar, published with GitHub Pages from the `master` branch at <https://akshaim.github.io/>.

It is plain HTML with one stylesheet. There is no build step and nothing to install.

## Preview locally

```sh
python3 -m http.server 8000
```

Then open <http://localhost:8000/>.

## To do

- **Update "Latest posts" automatically.** Today the list is edited by hand. Planned: a GitHub Actions workflow that reads the public HackMD profile, rewrites the list in `index.html` and commits it. It should run weekly, keep its own schedule alive (GitHub pauses scheduled workflows after 60 days without repository activity), offer a "Run workflow" button for an immediate refresh, and list only notes carrying a chosen tag so that personal notes never appear.
