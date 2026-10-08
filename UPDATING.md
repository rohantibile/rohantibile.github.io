# Updating your portfolio after it is live

Your site is the repo `rohantibile/rohantibile.github.io`. Every commit to `main` redeploys it automatically in about a minute.

## Three ways to change it
**A. In the browser (best for text edits)**
1. Open the repo on GitHub and press the `.` key. This opens the repo in a full online editor.
2. Open `index.html`, press Ctrl+F (Cmd+F on Mac) to find the text you want, change it.
3. Click the Source Control icon, type a short message such as "Update projects", and commit.

**B. Replace a file**
1. In the repo click **Add file → Upload files** and drag in the new file, for example a new video.
2. Use the same file name and folder. GitHub overwrites the old one. Commit.

**C. On your computer (best for bigger changes)**
```
git clone https://github.com/rohantibile/rohantibile.github.io.git
cd rohantibile.github.io
python -m http.server 8000      # preview at http://localhost:8000
git add .
git commit -m "Update portfolio"
git push
```

## Check the deploy
- Open the repo's **Actions** tab. A run named "pages build and deployment" turns green when the site is updated.
- If you still see the old page, hard refresh with Ctrl+Shift+R (Cmd+Shift+R on Mac).

## What to edit, and where in `index.html` (search for these text snippets)
| To change | Search for |
|---|---|
| Email, phone, LinkedIn | `tibilerohan3` |
| Hero text and tagline | `class="lede"` |
| Projects, results and charts | `var PROJ=[` |
| The request tracer's JSON answers | `var API={` |
| Skills graph (nodes and links) | `node('me'` |
| The Java class under the graph | `var L=[` |
| Impact numbers and the career timeline | `var I=[` and `career timeline` |
| Experience table | `SELECT * FROM experience` |
| Page title and link preview text | the `<title>` and `og:` lines at the top |

## Swap the intro video
Put your clip in the `media` folder with these exact names, keeping each file under about 5 MB:
```
ffmpeg -i myvideo.mp4 -c:v libx264 -crf 28 -pix_fmt yuv420p -movflags +faststart media/intro.mp4
ffmpeg -i myvideo.mp4 -c:v libvpx-vp9 -crf 38 -b:v 0 media/intro.webm
ffmpeg -ss 1 -i myvideo.mp4 -frames:v 1 media/poster.jpg
```
Portrait 3:4 framing fits the card best.

## Keep GitHub and the portfolio in sync
When a number or job changes, update three places the same day: the resume, `index.html`, and the profile `README.md` (and its `assets/impact-*.svg` and `assets/timeline-*.svg` if the numbers or dates changed).

## If you want Claude to make the change
Send the new details and the current `index.html`. You will get a new `index.html` back to upload with method B.
