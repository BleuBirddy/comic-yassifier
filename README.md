# Comic Yassifier

Turns a CBZ comic into an `.xtch` file for the Xteink X3 e-reader: bigger
speech bubbles, smart page splits and crisp 4-shade e-ink output.

Use it here: <https://bleubirddy.github.io/tools/comic-yassifier/>

## What it does

- **Two styles.** Classic keeps full-contrast art with bubbles up to 1.6×.
  Light & clear softens the blacks, grows bubbles up to 1.7× and keeps the
  lettering bold.
- **Preview.** After converting, step through the screens as the X3 will show
  them. Dropping an existing `.xtch` previews it without converting.
- **Private.** The comic is read and converted in your browser and is never
  uploaded.

Read the result on the X3 turned sideways (rotate clockwise).

## How it works

The whole tool is one file, `index.html`. The conversion code is Python and
runs in the browser through [Pyodide](https://pyodide.org) 0.27.2 with NumPy,
SciPy and Pillow. The first visit downloads those from the jsDelivr CDN (tens
of MB); after that the browser has them cached. That download is the only
thing the page asks the network for.

## Run it yourself

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000/>. It needs to be online the first time, to
fetch Pyodide.

The "Bleubirddy tools" link and the tab icon point at `/tools.html` and
`/favicon.svg` on bleubirddy.github.io. Change or remove them if you host it
somewhere else.

## License

MIT, see [LICENSE](LICENSE).
