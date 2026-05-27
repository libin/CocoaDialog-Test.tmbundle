# CocoaDialog Test.tmbundle

A TextMate bundle that smoke-tests every dialog control exposed by
[`swift-cocoadialog`](https://github.com/libin/swift-cocoadialog) — a clean-room,
MIT-licensed Swift+AppKit reimplementation of the original
[cocoadialog](https://github.com/cocoadialog/cocoadialog) 3.0 binary, drop-in
compatible with TextMate's Bundle Support.

Each command pops the corresponding dialog and prints the captured result back
to an HTML output window.

## Commands

| #  | Control      | Notes                                                       |
|----|--------------|-------------------------------------------------------------|
| 01 | about        | About dialog                                                |
| 02 | msgbox OK    | Plain message + OK                                          |
| 03 | msgbox Yes/No| Two-button confirmation                                     |
| 04 | question     | Yes/No/Cancel alias                                         |
| 05 | input        | Single-line input with default value                        |
| 06 | secure-input | Password input                                              |
| 07 | dropdown     | NSPopUpButton picker                                        |
| 08 | radio        | Radio buttons                                               |
| 09 | checkbox     | Checkboxes                                                  |
| 10 | slider       | Live integer/float slider                                   |
| 11 | open file    | NSOpenPanel                                                 |
| 12 | open dir     | NSOpenPanel `--select-only-directories`                     |
| 13 | open multi   | NSOpenPanel `--select-multiple`                             |
| 14 | save         | NSSavePanel                                                 |
| 15 | filesave     | `filesave` alias                                            |
| 16 | fileselect   | `fileselect` alias                                          |
| 17 | textbox      | Multi-line editable; ⌘⏎ submits                             |
| 18 | progressbar  | stdin-driven progress; closes on EOF                        |
| 19 | icon         | `--icon` SF Symbol / semantic name                          |
| 20 | markdown     | Inline markdown in `--header` / `--message`                 |
| 21 | timeout      | `--timeout` auto-close                                      |
| 22 | size %       | `--width 60%` / `--height 25%` screen-relative              |
| 23 | json output  | `--json` structured output                                  |
| 24 | radio with-input | Radio + inline single-line freeform input               |
| 25 | radio multiline  | Radio + inline multi-line text view (⌘⏎ submits)         |
| 26 | checkbox with-input | Checkboxes + freeform input row                      |
| 27 | radio recommended | `--recommended` pre-check + muted `(recommended)` suffix |
| 28 | auto-width    | Long multi-line shell command — panel grows up to 70% width |
| 29 | recommended+input | `--recommended` combined with inline `--with-input`     |

## Requirements

- TextMate Bundle Support providing `$TM_SUPPORT_PATH/bin/CocoaDialog.app`.
- macOS 14+.
- The `CocoaDialog` binary inside that `.app` should be the
  [`swift-cocoadialog`](https://github.com/libin/swift-cocoadialog) build
  (`swift build -c release` then copy `.build/release/cocoadialog` over
  `CocoaDialog.app/Contents/MacOS/CocoaDialog`).

## License

MIT — see `LICENSE`.
