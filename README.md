# juzigenius-data

Stroke-order data for 9,531 Chinese characters, as used by
[JuziGenius](https://juzigenius.com), published here so that it stays freely
available to everyone under the **Arphic Public License**.

## What is here

| File | What it is |
|---|---|
| `stroke_data.json` | Stroke paths and medians for each character, one JSON object keyed by character. |
| `stroke_data.index.json` | Byte offsets into `stroke_data.json`, so one character can be read without parsing the whole file. |
| `ARPHICPL.TXT` | The Arphic Public License. It must accompany the data wherever it goes. |
| `THIRD-PARTY-LICENSES.md` | Attribution and provenance for all the third-party data JuziGenius uses. |

## Where the data comes from

- Arphic Technology Co., Ltd. — the AR PL UMing and AR PL KaitiM fonts, © 1999,
  released under the Arphic Public License.
- [Make Me a Hanzi](https://github.com/skishore/makemeahanzi) — extracted stroke
  graphics and medians from those fonts.
- [hanzi-writer-data](https://github.com/chanind/hanzi-writer-data) — repackaged
  them for [Hanzi Writer](https://github.com/chanind/hanzi-writer).

## What was changed

Modified by JuziGenius on 2026-09-13:

1. Reduced to the 9,531 characters the application can present, omitting the
   rest of the upstream set.
2. Repacked from the upstream per-character files into a single JSON object
   with compact separators, indexed by byte offset in `stroke_data.index.json`.

Stroke paths, medians and glyph geometry are unaltered — only which characters
are included and how they are packaged. The same notice is carried inside
`stroke_data.json` itself, under its `_modifications` key.

## License

The data is distributed under the Arphic Public License (`ARPHICPL.TXT`). You
may copy, modify and redistribute it, commercially or not, under that license's
terms: the license and copyright notices travel with the data, changes are
documented, and modified versions stay under the same license.

This repository contains data only. JuziGenius's own source code is not
published and is not covered by anything here.

## Corrections

Attribution errors are bugs. If something is miscredited, mis-licensed or
missing, please open an issue here or write to <support@juzigenius.com>.
