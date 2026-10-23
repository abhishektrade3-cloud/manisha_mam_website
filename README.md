# Dr Manisha G. Kulthe — faculty website

A static site (React, hand-written CSS, no build step) whose content lives in `content/site.json`.
Dr Kulthe edits that file through a CMS at `/admin/`, with login and forms — no code, no GitHub knowledge.

## Files

    index.html            the whole website, including the percolation explorer (React, inlined CSS)
    content/site.json     all editable content (text, publications, projects, gallery)
    images/               photos used on the site
    admin/index.html      the CMS (Decap)
    admin/config.yml      which fields the CMS shows
    netlify.toml          hosting config
    robots.txt            keeps /admin out of search engines

## Putting it online (about 20 minutes, free)

1. **GitHub.** Create a new repository, e.g. `manisha-kulthe-site`. Upload every file and folder here, keeping the structure. The default branch must be called `main`.
2. **Netlify.** Sign in at netlify.com with GitHub, choose *Add new site → Import an existing project*, pick the repository, leave the build command empty and the publish directory as `.`, and deploy. The site goes live at something like `manisha-kulthe.netlify.app`.
3. **Set the URL.** In `admin/config.yml`, replace the three `https://example.netlify.app` lines with the real address, and commit.
4. **Turn on logins.** In Netlify: *Site configuration → Identity → Enable Identity*. Under *Registration*, choose **Invite only**. Under *Services → Git Gateway*, press **Enable Git Gateway**.
5. **Invite her.** *Identity → Invite users*, enter her COEP email. She gets a mail, sets a password, and can then open `yoursite.netlify.app/admin/` to edit.
6. **Custom domain (optional).** Buy a domain (GoDaddy, Namecheap, about ₹900/year) and add it under *Domain management*. HTTPS is automatic.

## How she edits

Open `/admin/`, log in, click **Website content → All content**. Every section is a form:
headline, about paragraphs, portrait, gallery photos, publications, projects, awards,
memberships, experience and qualifications. Lists can be reordered by dragging.
Press **Publish** and the site rebuilds in under a minute.

The front-page portrait is the *Portrait photo* field. A head-and-shoulders photo in portrait
orientation works best; the site crops it to 4:5 and keeps the face in the upper third.

Uploading a photo: open *Gallery photos → Add photo*, choose the file, write a caption,
and pick a Section: **Events & felicitations**, **Department & campus**, **Industry & MoUs**,
or **Research highlights** (figures and results from published papers go in the last one).
The Moments slideshow on the home page shows the first eight photos that are not
research highlights, so drag a photo to the top of the list to feature it.

## Editing without the CMS

`content/site.json` is plain text. Editing it on GitHub and committing updates the site too.

## Notes

- The site is public; `/admin/` needs a login.
- `index.html` falls back to built-in content if `content/site.json` is missing, so the page never breaks.
- Keep uploaded photos under about 1 MB each for fast loading.
