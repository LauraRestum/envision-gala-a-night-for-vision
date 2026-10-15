# A Night for Vision: guest page

A one-page, phone-friendly site for Envision Gala 2026 guests to watch the
films and see the program. It is plain HTML with no build step.

## Deploy on Vercel

1. In Vercel, choose **Add New > Project** and import this repository.
2. Framework preset: **Other**. Leave the build command and output directory empty.
3. Deploy. Vercel serves `index.html` at the root.

Every push to the production branch redeploys automatically. Other branches get
their own preview link.

## Updating the page

All content is in one block near the bottom of `index.html`, between
`CONTENT` and `END CONTENT`:

- `FILMS`: title, length, who appears, a short description, and the video link.
  Put a public link in `watch` (and `described` for an audio-described cut).
  YouTube (unlisted is fine), Dropbox links shared as "Anyone with the link",
  and direct `.mp4` addresses play right on the page. Other links open in a
  new tab. An empty link shows "Video coming soon".
- `PROGRAM`: the evening in order. `time` is optional; `film: 1` to `5` adds a
  "Watch it" link to that film.
- `SPONSORS`: tier and names.

Nothing else needs to change.
