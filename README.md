# Khoi Ngo Photography

Portfolio site for Khoi Ngo (Harry), portrait photographer in Sydney.
It's a single static page (`index.html` + the `images/` folder), so it runs on GitHub Pages with no build step.

## Put it online with GitHub Pages

1. Sign in at github.com and click **New repository**.
2. Name it `YOUR-USERNAME.github.io` (use your real GitHub username).
   This makes the site live at `https://YOUR-USERNAME.github.io/`.
   Any other name also works, the address is then `https://YOUR-USERNAME.github.io/REPO-NAME/`.
3. Set it to **Public**, then click **Create repository**.
4. On the new repo page, click **uploading an existing file**.
5. Unzip `khoi-portfolio.zip` and drag everything inside the `khoi-portfolio` folder
   (`index.html`, `README.md`, `.nojekyll` and the whole `images` folder) into the upload box.
   On a Mac, press Cmd+Shift+. in Finder to see the hidden `.nojekyll` file. It's optional, the site works without it.
6. Click **Commit changes**.
7. Go to **Settings → Pages**. Under "Build and deployment", set Source to **Deploy from a branch**,
   choose the **main** branch and the **/ (root)** folder, then **Save**.
8. Wait a minute or two and open the address from step 2.

## Change the words

Everything is in `index.html`. On GitHub you can open the file and click the pencil icon to edit it in the browser.

- Hero text: search for `Portrait photographer in Sydney.`
- Shoot titles and descriptions: search for `class="chapter-title"` and `class="chapter-note"`.
  Each shoot's title also appears once in the Work list near the top (`class="idx-title"`).
- About and experience: search for `id="about"`.
- Contact links: search for `id="contact"`.

## Add or swap a photo

Each photo exists in two sizes: `images/NAME-s.jpg` (about 900px, for the grid) and `images/NAME-l.jpg` (about 2000px, for the full-screen viewer).

1. Export your photo twice at those sizes (Lightroom, Photoshop or squoosh.app all work) and upload both to `images/`.
   If you only have one file, that's fine, use the same file name in both places below.
2. Copy an existing `<figure class="frame" ...> ... </figure>` block inside the shoot you want and change:
   - `--ar:` to the photo's width divided by its height (portrait 4:5 = `0.8`, 3:4 = `0.75`, landscape 3:2 = `1.5`)
   - `data-full`, `src` and `srcset` to your file names
   - `width` and `height` to the photo's pixel size
   - `alt` to a short description of the photo
   - the "photo X of Y" counts, and the photo count in the shoot header and the Work list
3. Commit. The rows rearrange themselves to fit.

To add a whole new shoot, copy an entire `<section class="chapter" ...>` block, give it a new `id`,
and add a matching row to the Work list (`<ul class="index">`).

## Custom domain (optional)

Buy a domain, then in **Settings → Pages → Custom domain** enter it and follow GitHub's DNS instructions.
