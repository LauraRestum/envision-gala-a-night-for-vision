# A Night for Vision: guest page

A one-page, phone-friendly site for Envision Gala 2026 guests to watch the
films and see the program. It is plain HTML with no build step.

## Deploy on Vercel

1. In Vercel, choose **Add New > Project** and import this repository.
2. Framework preset: **Other**. Leave the build command and output directory empty.
3. Deploy. Vercel serves `index.html` at the root.

Every push to the production branch redeploys automatically. Other branches get
their own preview link.

## What's here

- `index.html`: the films, plus a big "View the program" button.
  The film list (title, length, file name) is the `FILMS` block in the script.
- `program.html`: the printed program, one page at a time, with Back and Next
  buttons. Pages are `program/page-01.jpg` to `page-20.jpg`; each page's
  description for screen readers is in the `PAGES` list.

## Videos

The files in `videos/` are 960x540 H.264 copies made for phones. The full
quality masters stay in Dropbox under `Gala Video Production`:

Posters are the matching `.jpg` files.

| File | Source |
|---|---|
| `legacy.mp4` | `Legacy Participant - Aubree, Hashim & Steven/FINAL/Legacy_Video_FINAL_1080p.mp4` |
| `water-street.mp4` | `Water St/FINAL/WaterSt_Gala_Final.mp4` |
| `heathers-camp.mp4` | `Heathers Camp/Heathers Camp 2026 90 Sec.mp4` (web copy from the asset dashboard) |
| `full-circle.mp4` | `ECDC - Adah & Teresa/FINALS/ECDC_Adah_FullCircle_FINAL.mp4` (web copy from the asset dashboard) |
| `full-circle-described.mp4` | `ECDC - Adah & Teresa/FINALS/ECDC_Adah_FullCircle_AUDIO_DESCRIBED_FINAL.mp4` |
| `level-up.mp4` | `Level Up Video/Level Up 90 Sec.mp4` (web copy from the asset dashboard) |

To replace one, export a new copy with:

    ffmpeg -i MASTER.mp4 -vf scale=960:-2 -c:v libx264 -crf 25 -pix_fmt yuv420p -c:a aac -b:a 128k -movflags +faststart videos/NAME.mp4

Nothing else needs to change.
