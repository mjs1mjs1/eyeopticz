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

1. Unzip `eyeopticz-site.zip` on your computer. You get a folder called `eyeopticz`.
2. On GitHub, click the **+** at the top right, then **New repository**.
3. Name it `eyeopticz`. Choose **Public** (it is your public website anyway).
   Leave the other boxes unticked. Click **Create repository**.
4. On the next page, click the link **uploading an existing file**.
5. Open the unzipped `eyeopticz` folder, select **everything inside it**
   (not the folder itself), and drag it onto the GitHub page.
   - On a Mac, files starting with a dot (`.gitignore`, `.ruby-version`) are
     hidden. Press **Cmd + Shift + .** in Finder to show them, and include them.
6. Wait for the upload to finish, then click **Commit changes** at the bottom.

## Step 3. Connect GitHub to Cloudflare Pages (10 minutes)

1. Log in to https://dash.cloudflare.com.
2. In the left menu choose **Workers & Pages**, then **Create**
   (or **Create application**), then the **Pages** tab,
   then **Connect to Git**.
3. Choose **GitHub**, sign in, and allow Cloudflare to see the `eyeopticz`
   repository. Select it and click **Begin setup**.
4. Fill in the build settings exactly like this:
   - **Project name:** `eyeopticz`
   - **Production branch:** `main`
   - **Framework preset:** `Jekyll`
   - **Build command:** `bundle exec jekyll build`
   - **Build output directory:** `_site`
5. Click **Save and Deploy**. The first build takes 2 to 4 minutes.
6. When it says "Success", click the link it shows
   (something like `eyeopticz.pages.dev`). That is your site, working.

## Step 4. Attach eyeopticz.com (5 minutes, then up to an hour to take effect)

Because your domain is already at Cloudflare, this is two clicks.

1. In your Pages project, open the **Custom domains** tab.
2. Click **Set up a custom domain**, type `eyeopticz.com`, and confirm.
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

Cloudflare shows the error under your project's **Deployments** tab.
The most common causes are a typo in `_config.yml` or `_data/publications.yml`
(these are sensitive to spaces and quotation marks). Undo your last change on
GitHub and try again. If the error mentions Ruby, add an environment variable
in the Pages project settings: `RUBY_VERSION` = `3.3.6`.
