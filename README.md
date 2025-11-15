# Saudi eLeague Leaderboard

Static leaderboard page that looks similar in layout and style to the Saudi Leagues leaderboard page, and reads team data from a Google Sheet.

The page is a single file called `index.html`. It can be deployed as a static site on Vercel.

## 1. Google Sheet setup

Create a Google Sheet with the following columns:

- Column A: Rank  
- Column B: Logo URL  
- Column C: Team name  
- Column D: Points  

Example:

| Rank | Logo URL                       | Team name      | Points |
|------|--------------------------------|----------------|--------|
| 1    | https://example.com/logo1.png  | Team One       | 120    |
| 2    | https://example.com/logo2.png  | Team Two       | 95     |

Then:

1. Click the **Share** button.
2. Under **General access**, choose **Anyone with the link**.
3. Make sure the permission is **Viewer**.

From the sheet URL, copy the Sheet ID.

Example:

`https://docs.google.com/spreadsheets/d/1AbCdEfGh1234567890XYZ/edit?usp=sharing`

The Sheet ID here is:

`1AbCdEfGh1234567890XYZ`

Also note the sheet tab name, for example `Leaderboard`.

## 2. Configure the HTML file

In `index.html` you will find these lines near the top of the script:

```js
const SHEET_ID = "YOUR_SHEET_ID_HERE"; // استبدل هذا بالقيمة الصحيحة
const SHEET_NAME = "Leaderboard";      // استبدل هذا باسم الشيت اذا كان مختلفا
```

Replace:

- `YOUR_SHEET_ID_HERE` with your real Sheet ID.
- `Leaderboard` with the exact tab name if different.

Save the file.

If you do not edit locally, you can edit this directly in GitHub in the browser.

## 3. Put on GitHub

1. Create a new repository on GitHub.
2. Upload `index.html` and `README.md` to the root of the repo.
3. Commit.

## 4. Deploy on Vercel

1. Log in to Vercel using your GitHub account.
2. Click **Add New Project** and import the repository.
3. Vercel will detect a static site.
4. No build command is needed. The default output directory is the project root.
5. Click **Deploy**.

Vercel will give you a URL like:

`https://your-project-name.vercel.app`

Opening that URL will show the leaderboard and it will always read the latest data from your Google Sheet each time the page loads.
