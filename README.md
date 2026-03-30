# MacPhail Family Genealogy — GitHub Pages

A free, shareable genealogy query tool for the MacPhail family of Argyle Shore, PEI.

## What's in this repo

```
index.html        — the website (browse + chat)
data/
  family.json     — all family data (add to this as you scan more pages)
README.md         — this file
```

## Setting up GitHub Pages (one time)

### Step 1 — Create the repo
1. Go to github.com and sign in
2. Click the **+** icon top right → **New repository**
3. Name it: `macphail-genealogy`
4. Set it to **Public** (required for free GitHub Pages)
5. Click **Create repository**

### Step 2 — Upload the files
1. On your new repo page, click **Add file → Upload files**
2. Drag in `index.html` and the `data` folder (with `family.json` inside)
3. Click **Commit changes**

### Step 3 — Enable GitHub Pages
1. In your repo, click **Settings**
2. Scroll down to **Pages** in the left sidebar
3. Under **Source**, select **Deploy from a branch**
4. Set Branch to **main**, folder to **/ (root)**
5. Click **Save**
6. Wait about 60 seconds, then your site is live at:
   `https://YOUR-GITHUB-USERNAME.github.io/macphail-genealogy`

That URL is shareable with anyone — no login required.

## Getting your Gemini API key (free)

1. Go to **aistudio.google.com**
2. Sign in with your Google account
3. Click **Get API key** in the left sidebar
4. Click **Create API key**
5. Copy the key

When you visit the website, paste the key into the "Gemini API Key" box at the top of the
"Ask a Question" tab and click Save. It stores in your browser — you only do this once per device.
Family members who visit the site will each need to paste their own key (or you can share yours).

## Adding more data as you scan pages

When you have new scanned PDF pages:

1. Start a new Claude conversation
2. Upload the PDF pages
3. Say: "Extract all people from these pages as JSON matching this format:" 
   then paste in a few example records from family.json
4. Claude will return new JSON records
5. Open family.json, paste the new records into the "people" array
6. Save and re-upload to GitHub (drag and drop again, commit)
7. Site updates within a minute

## The data format

Each person looks like this:
```json
{
  "id": "MP114154d5",
  "name": "James Brian MacPhail",
  "known_as": "Brian",
  "born": "1960-11-25",
  "birthplace": "Charlottetown, PEI",
  "died": null,
  "father": "MP114154d",
  "spouses": [{"name": "Corrinne Anne McDonald", "married": "1985-06-29"}],
  "children": ["MP114154d51", "MP114154d52", "MP114154d53"],
  "occupation": "Sales manager",
  "notes": "Any extra biographical detail goes here."
}
```

The `id` field uses the book's MP number system exactly.
The `father` field links to a parent's `id` — this is how relationships are traced.
