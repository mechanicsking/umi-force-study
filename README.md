# Project page (GitHub Pages)

Videos-first companion to the poster. Everything else lives on the poster itself.

## Publish (once)
    gh repo create <user>/umi-force-study --public --source=site --push   # or: git init in site/, push to a new repo
    gh api -X POST repos/<user>/umi-force-study/pages -f build_type=legacy -f 'source[branch]=main' -f 'source[path]=/'
    # URL: https://<user>.github.io/umi-force-study/

## Add the robot video later
    cp <robot_run>.mp4 site/media/robot.mp4       # keep < 100 MB; re-encode with ffmpeg -crf 28 if needed
    # replace the .soon placeholder in index.html with a <video> block like the first one, then git push

## Poster QR
`custom/scripts/poster/build_poster.py` has a marker comment in the Introduction block; generate the QR with
`qrcode` from the Pages URL to `outputs/figures/qr_project_page.png` and re-add the picture there.
