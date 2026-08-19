# Manitowoc Card Show — setup guide

This site has a normal page (`index.html`) plus a private admin page
(`/admin`) where you can sign in and edit the show details, table
count, and photos through a form — no code editing needed after
today.

## What's in this folder
- `index.html` — the public website
- `content/site.json` — the editable data (date, hours, prices, table
  count, contacts, photos). The admin page edits this file for you.
- `admin/index.html` and `admin/config.yml` — the admin editor itself
- `images/uploads/` — where your uploaded photos will land

## One-time setup (about 20–30 minutes)

### 1. Create a GitHub account and repository
1. Go to github.com and sign up (free) if you don't have an account.
2. Click "New repository." Name it something like `manitowoc-card-show`.
   Keep it Public. Don't add a README (we already have files).
3. On the new repo's page, use "Add file → Upload files" and drag in
   everything from this folder (`index.html`, the `content` folder, the
   `admin` folder, the `images` folder). Commit the upload.

### 2. Connect the repo to Netlify (free hosting)
1. Go to netlify.com and sign up using your GitHub account.
2. Click "Add a new site → Import an existing project → GitHub," and
   pick your `manitowoc-card-show` repo.
3. Leave the build settings blank (no build command, publish directory
   is the root `/`). Click Deploy. Netlify gives you a live URL like
   `manitowoc-card-show.netlify.app` — that's your real website.
   (You can point your own domain at it later if you get one.)

### 3. Turn on Identity and Git Gateway (this is what makes /admin work)
1. In your Netlify site dashboard, go to **Site configuration → Identity**
   and click **Enable Identity**.
2. Still under Identity, go to **Registration** and set it to
   **Invite only** (so random people can't sign themselves up).
3. Go to **Services → Git Gateway** and click **Enable Git Gateway**.
   This lets the admin page save changes back to GitHub on your behalf.
4. Go to the **Identity** tab and click **Invite users**. Enter your own
   email (and Seth's, if you want him to be able to edit too). You'll
   get an email invite — click it to set a password.

### 4. Log in and edit
1. Visit `your-site.netlify.app/admin/`.
2. Log in with the account you just set up.
3. You'll see a form for "Site content" — event details, vendor table
   count, contacts, and a gallery section where you can drag in photos.
4. Hit **Publish** on any change and it goes live on the real site
   within a minute or two.

## Updating the table count day-to-day
Once this is set up, you never need to touch code again — go to
`/admin`, open "Site content," change **Tables reserved so far**, and
publish. The green/amber/red banner on the site updates itself.

## Adding or swapping photos
In `/admin`, open the **Gallery photos** list. Each row has an image
upload and a caption. Add a row for a new photo, or click into an
existing row to replace its image. The homepage carousel picks up
whatever's there automatically, in order.
