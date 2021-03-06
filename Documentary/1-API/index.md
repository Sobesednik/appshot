## ImageMagic convert

The `convert` utility from ImageMagic library should be installed to allow saving optimized GIFs.

```sh
brew install imagemagic
```

Otherwise, un-optimized records can be taken with `-g` flag.

%~%

<!-- ### `--focus`, `-F`

Bring the window to the foreground using a snippet:

```applescript
tell app "Finder"  to set frontmost of process processName to true
```

```sh
appshot --app iTunes --capture --focus
``` -->

<!-- After getting information about windows via the same process as `list` mode, spawn `screencapture`, passing the id of the first found window. Windows do not have to be in foreground, and can appear dimmed. To solve this, add `--focus` flag to additionally run `./etc/active.py` which will use _applescript_: . -->

<!--
The table with found windows will be printed as well, unless you
set the `--quiet` flag. -->

<!-- ## Screenshots

![appshot command](https://sobesednik.co/appshot/appshot.png)

![appshot --app App command](https://sobesednik.co/appshot/app.png)

![appshot --no-empty-title command](https://sobesednik.co/appshot/no-empty-title.png)

![appshot --app App --title Title command](https://sobesednik.co/appshot/list-app-title.png)

![appshot --capture command](https://sobesednik.co/appshot/capture.png) -->

<!-- ### Example

```bash
appshot \
  --app Chrome \
  --title zoroaster \
  --capture \
  --no-shadow \
  --screenshots-dir ~/appshots \
  --format jpg \
  --focus \
```

![captured browser window with zoroaster website](https://sobesednik.co/appshot/capture.jpg) -->

<!-- ## Explanation

Data comes encoded as JSON string from `etc/run.py`, which uses Quartz to get information about windows.

```
[[64, "Flux", "Item-0", 526], [26, "SystemUIServer", "AppleBluetoothExtra", 394], [30, "SystemUIServer", "AirPortExtra", 394], [46, "SystemUIServer", "DisplaysExtra", 394], [34, "SystemUIServer", "AppleTextInputExtra", 394], [38, "SystemUIServer", "AppleClockExtra", 394], [42, "SystemUIServer", "AppleUser", 394], [54, "Spotlight", "Item-0", 464], [24, "SystemUIServer", "Siri", 394], [22, "SystemUIServer", "NotificationCenter", 394], [3, "Window Server", "Menubar", 158], [20,
"Dock", "Dock", 391], [314, "iTerm2", "1. bash", 1219], [2437, "Google Chrome", "", 372], [2438, "Google Chrome", "Logfile by z-vr \u00b7 Pull Request #1 \u00b7 Sobesednik/browsershot", 372], [297, "iTunes", "iTunes", 1137], [2778, "Finder", "logs", 395], [2510, "Finder", "58dc0ebb-12d3-42d0-8f68-73ebe6821f44", 395], [1554, "Activity Monitor", "Activity Monitor (All Processes)", 25318], [1263, "App Store", "App Store", 19532], [4, "Window Server", "Backstop Menubar", 158], [21,
"Finder", "", 395], [18, "Dock", "Desktop Picture - IMG_2586.JPG", 391], [2, "Window Server", "Desktop", 158]]
```

JSON-encoded array with records like `[winid, app, title, pid]` is printed to `stdout` by Python and deserialised by Node. Once window id is found, we call `screecapture -l<winid>` to take a screenshot of an app. -->

<!-- ## TODO:

 - add support for export of all fields from python, and provide interface between python script and node
 - add cli help
 - use more `screencapture` options, such as formats other than `jpg` and `png`, `-P`,  `-T`, `-c` -->

<!-- ## Readings

[stackoverflow - WindowInfo list of keys][2] -->
