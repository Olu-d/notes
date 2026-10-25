# glowi-media

Temporary public host for finished Glowi.Africa carousel slides and reels, so Metricool can fetch them from public `raw.githubusercontent.com` URLs. Files are deleted once Metricool has copied them.

## Layout

- IG images (2160x2700): `glowi-media/<post_name>/`
- TikTok copies (1080 wide): `glowi-media/<post_name>/tt/`
- Reels: mp4 files in `glowi-media/<post_name>/`

## Naming

- Slides: `glowi_<post_name>_slideNN.jpg` (NN = 01, 02, ...)
- Reels: `glowi_<post_name>.mp4`

## Process

1. Add the files under `glowi-media/<post_name>/` (and `tt/` for TikTok copies).
2. Commit and push to master: `git push origin HEAD:master`
3. Verify every raw URL returns HTTP 200:
   `https://raw.githubusercontent.com/Olu-d/notes/master/glowi-media/<post_name>/<file>`
   e.g. `curl -s -o /dev/null -w "%{http_code}" <url>`
4. Give the URLs to Metricool. Metricool copies each file to `static.metricool.com`.
5. Once Metricool has copied them (media shows a `static.metricool.com` URL), delete the files from the repo and push, so nothing lingers publicly.

The repo is public: only host content that is meant to be published.
