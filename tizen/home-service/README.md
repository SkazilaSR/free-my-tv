# Home service (from AeroTizen)

`python3 tizen/build.py --home` packs Free My TV as `DclHome001.Home` with this background service as
`DclHome001.Watcher`, so AeroTizen's CLI can make it the TV's native Home (`aerotizen home apply --yes`) and
restore Samsung's (`aerotizen home restore --yes`).

The files are AeroTizen's `launcher/service/` (github.com/helalaou/AeroTizen, commit c62f60c, MIT: see LICENSE),
unchanged. Its Home writer only accepts that app id and asks this service (http://127.0.0.1:47790) for the
handoff; until Native Home is applied, it also brings the app back when Samsung Home covers it. The page tells it
what it opens (`TV.homeService` in web/tv.js), as AeroTizen's launcher does. Its diagnostics are left out
(optional there).
