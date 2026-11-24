# Setting up eyeopticz.com

This folder is a complete website. You put it on GitHub (free), and Cloudflare
Pages (free) turns it into the website at eyeopticz.com. After that, whenever you
change a file on GitHub, the website updates itself within a minute or two.

Allow about an hour the first time.

---

## Step 1. Create a GitHub account (5 minutes)

1. Go to https://github.com/signup and create a free account.
   Your username will appear only in GitHub addresses, not on your website.

## Step 2. Create a repository and upload the files (10 minutes)

A "repository" is just a folder on GitHub.

1. Unzip `eyeopticz-site.zip` on your computer (on Windows: right-click it and
   choose **Extract All…**; do not drag from inside the zip). You get a folder called `eyeopticz`.
2. On GitHub, click the **+** at the top right, then **New repository**.
3. Name it `eyeopticz`. Choose **Public** (it is your public website anyway).
   Leave the other boxes unticked. Click **Create repository**.
4. On the next page, click the link **uploading an existing file**.
5. Using **Chrome, Edge or Firefox** (not Safari, which drops the folders),
   open the unzipped `eyeopticz` folder, select **everything inside it**
   (not the folder itself; Ctrl + A on Windows), and drag it onto the GitHub page.
   Do not use the "choose your files" button, which cannot pick folders.
   Before committing, check the list shows paths such as
   `_layouts/page.html` and `_papers/nodal-points-and-the-eye.md`.
   - On a Mac, files starting with a dot (`.gitignore`) are
     hidden. Press **Cmd + Shift + .** in Finder to show them, and include them.
6. Wait for the upload to finish, then click **Commit changes** at the bottom.

## Step 3. Connect GitHub to Cloudflare (10 minutes)

1. Log in to https://dash.cloudflare.com.
2. In the left menu choose **Workers & Pages**, then **Create application**.
3. Choose **Import a repository** (or **Connect to Git**), pick **GitHub**,
   sign in, and select the `eyeopticz` repository.
4. Fill in the settings exactly like this:
   - **Project name:** `eyeopticz`
   - **Build command:** `bundle install && bundle exec jekyll build`
   - **Deploy command:** `npx wrangler deploy`
   - Leave anything else as it is.
   The file `wrangler.jsonc` in the repository tells Cloudflare that the
   finished website is in the `_site` folder, so you do not need to enter
   an output directory.
5. Click **Deploy**. The first build takes 2 to 4 minutes.
6. When it succeeds, Cloudflare shows a link ending in `workers.dev`.
   That is your site, working.

If you later find a screen that offers **Pages** instead (it asks for a
"Framework preset" and a "Build output directory"), that also works:
build command `bundle install && bundle exec jekyll build`, output
directory `_site`.

## Step 4. Attach eyeopticz.com (5 minutes, then up to an hour to take effect)

Because your domain is already at Cloudflare, this is two clicks.

1. In your project, open **Settings**, then **Domains & Routes**
   (on a Pages project it is the **Custom domains** tab).
2. Click **Add**, choose **Custom domain**, type `eyeopticz.com`, and confirm.
   Cloudflare adds the DNS record for you.
3. Do it again for `www.eyeopticz.com`, so both addresses work.
4. It can take a few minutes up to an hour before eyeopticz.com shows the site.

## Step 5. Tell Google about it (10 minutes)

1. Go to https://search.google.com/search-console and click **Add property**.
2. Choose **Domain**, type `eyeopticz.com`. Google shows a TXT record.
   Search Console usually offers to add it to Cloudflare automatically;
   otherwise add it in Cloudflare under **DNS > Records**.
3. Once verified, open **Sitemaps** and submit `sitemap.xml`.
4. On simpsonoptics.com, add a link to eyeopticz.com (for example
   "Research: eyeopticz.com"). Links from your existing site help Google
   find and trust the new one.

---

## Things to finish after it is live

These are all edits in GitHub: open the file, click the pencil icon, change it,
then click **Commit changes**. The site rebuilds automatically.

1. **Your contact email.** In `_config.yml`, fill in the `email:` line.
   It will be shown publicly on the site. Add your ORCID and Google Scholar
   links there too when you have them.
2. **Upload your PDFs.** Download the PDFs from your current Downloads page and
   upload them into the `files` folder using the names listed in
   `files/README.txt`. Until you do, the site links to the copies on
   simpsonoptics.com. Hosting them on eyeopticz.com is what lets Google
   Scholar list them.
3. **Abstracts.** Each paper has its own page in the `_papers` folder with a
   one- or two-sentence summary I wrote from the title and your site. Replace
   it with the real abstract, where the journal's copyright allows.
4. **Check the wording.** The topic pages are rewritten in plain language from
   your current site. Please check every statement. Edit freely.
5. **Missing DOI.** "Optical modeling of the entire visual field of the eye"
   (2023) needs its DOI: in `_papers/optical-modeling-entire-visual-field.md`
   and in `_data/publications.yml`.

## Where things are

(`wrangler.jsonc`, `Gemfile` and `Gemfile.lock` are settings files. You do not need to edit them.)

| To change... | Edit this file |
| --- | --- |
| Site name, your details, the menu | `_config.yml` |
| Home page | `index.md` |
| A topic page | `nodal-point.md`, `far-peripheral-vision.md`, `negative-dysphotopsia.md`, `history.md`, `about.md` |
| The publication list | `_data/publications.yml` |
| A paper's own page (summary, PDF, citation) | the file for it in `_papers/` |
| Colours and fonts | `assets/css/site.css` |

Pages are written in Markdown: `## Heading` makes a heading, `**bold**` makes
bold, `[text](https://link)` makes a link, and a blank line starts a new paragraph.

**Adding a new topic page:** copy `far-peripheral-vision.md`, rename it,
change the title, description and text, and add it to the `nav:` list in
`_config.yml` if you want it in the menu.

**Adding a new paper:** copy any file in `_papers/`, change the details, and
add a line for it in `_data/publications.yml`.

## If a build fails

Cloudflare shows the error under your project's **Deployments** tab
(click the failed deployment, then **View build log**).
The most common causes are a typo in `_config.yml` or `_data/publications.yml`
(these are sensitive to spaces and quotation marks). Undo your last change on
GitHub and try again. If the error mentions Ruby, add a build variable
under Settings > Build: `RUBY_VERSION` = `3.4`.

## Adding pictures

1. Upload the picture into the `assets/img` folder on GitHub (open the folder,
   then **Add file > Upload files**). JPG or PNG, ideally under 500 KB.
2. On the page where you want it, add this line:

       {% include image.html file="your-picture.jpg" caption="What it shows" %}

   Add `width="half"` inside the brackets for a smaller picture.
3. For a photo of yourself on the home and About pages, upload it as
   `assets/img/photo.jpg` and set `photo: photo.jpg` in `_config.yml`.

## Colours

The colours are listed at the top of `assets/css/site.css`. Each topic page
has its own colour (teal, amber, coral or indigo), set near the top of `_config.yml`.
