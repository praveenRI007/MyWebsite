# Praveen's Workspace

Personal portfolio built with [Hugo](https://gohugo.io/) and the
[PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.

Here is my website : [link](https://praveenri007.github.io/MyWebsite/)

## 1. Prerequisites

- [Hugo (extended)](https://gohugo.io/installation/) v0.128+ — `hugo version` should mention `extended`
- Git
- A GitHub account

## 2. First-time setup

```bash
# 1. unzip and cd into the project
cd MyWebsite

# 2. initialise git
git init
git branch -M main

# 3. add PaperMod as a theme submodule
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
git submodule update --init --recursive

# 4. test locally
hugo server -D
# open http://localhost:1313/MyWebsite/
```

If the local site looks right, push to GitHub:

```bash
git add .
git commit -m "initial commit"
git remote add origin https://github.com/<your-username>/MyWebsite.git
git push -u origin main
```

## 3. Edit `hugo.yaml` before pushing

Open `hugo.yaml` and replace these placeholders:

- `baseURL` — must be `https://<your-username>.github.io/<repo-name>/`
- `<your-github-username>` in `socialIcons` and `editPost`
- `you@example.com` in `socialIcons.email`

If you'll use a `username.github.io` repo (root site), set
`baseURL: "https://<your-username>.github.io/"` and skip the repo name.

## 4. Enable GitHub Pages

In your GitHub repo: **Settings → Pages → Build and deployment → Source:
GitHub Actions**. The workflow in `.github/workflows/hugo.yml` will
build and deploy on every push to `main`.

## 5. Adding content

### A new blog post

```bash
hugo new content blogs/my-new-post.md
```

Edit the file, change `draft: true` → `draft: false`, write your post
in Markdown, drop images into `static/images/blogs/`, and reference them
as `/images/blogs/your-image.jpg`.

### A new project

```bash
hugo new content projects/my-project.md
```

### A 3D model or drawing

1. Drop the image into `static/images/3d-model/` or `static/images/drawing/`
2. Open `content/3d-model/_index.md` or `content/drawing/_index.md`
3. Add a new line inside `<div class="gallery-grid">`:
   ```html
   <a href="/images/3d-model/new.jpg" target="_blank"><img src="/images/3d-model/new.jpg" alt="New piece"></a>
   ```

## 6. Dark / light mode

Already enabled. The toggle button appears in the top-right of the
header. Default behaviour follows the OS preference (`defaultTheme: auto`
in `hugo.yaml`). Change to `defaultTheme: dark` or `light` if you want
to force one.

## 7. Customising the look

Most things live in `hugo.yaml` under `params`. For deeper styling
changes, see the [PaperMod wiki](https://github.com/adityatelange/hugo-PaperMod/wiki).
