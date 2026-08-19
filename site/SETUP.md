# Setting up your admin login

This site now has a `/admin` page where you can log in and edit the event
details, table count, and photos through a form — no code required after
today. Getting it live takes about 20–30 minutes, one time.

## 1. Put the site on GitHub

1. Go to github.com and create a free account if you don't have one.
2. Create a new repository, e.g. `manitowoc-card-show`. Keep it Public.
3. Upload every file in this folder to that repository (drag-and-drop
   works fine on github.com — use "Add file > Upload files").
4. Open `admin/config.yml` in the repo, and change this line:
   `repo: YOUR-GITHUB-USERNAME/manitowoc-card-show`
   to your actual GitHub username, e.g. `repo: evanderk/manitowoc-card-show`.
   Commit the change.

## 2. Deploy it on Netlify (free)

1. Go to netlify.com and sign up (you can sign up with your GitHub account).
2. Click "Add new site" > "Import an existing project" > choose GitHub >
   pick your `manitowoc-card-show` repo.
3. Leave the build settings blank (no build command, publish directory
   is the root `/`) and click Deploy.
4. Netlify gives you a free web address like
   `manitowoc-card-show.netlify.app` — that's your live site. You can
   add a custom domain later if you want.

## 3. Turn on GitHub login for the admin page

1. In GitHub, go to Settings > Developer settings > OAuth Apps > New OAuth App.
   - Application name: Manitowoc Card Show Admin
   - Homepage URL: your Netlify site address
   - Authorization callback URL: `https://api.netlify.com/auth/done`
2. GitHub gives you a Client ID and Client Secret — copy both.
3. In Netlify, go to your site > Site configuration > Access control > OAuth,
   and click "Install provider" for GitHub. Paste in the Client ID and Secret.

## 4. Log in and edit

Go to `your-site-address.netlify.app/admin`, click "Login with GitHub,"
and you'll see a form for:
- Event date, hours, admission, parking, food & drink note, load-in time
- Table price, total tables, and how many are reserved
- Your and Seth's contact info
- Gallery photos (upload directly in the form — drag and drop)

Hit "Publish" after any change and it goes live on the site within about
a minute.

## Updating the table count without the CMS

If you ever want a fast manual edit, `content/site.json` in the repo has
a `vendors.reserved_tables` number — bump it and commit, and the banner
updates the same way.
