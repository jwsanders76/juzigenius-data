# Third-party licenses and attribution

JuziGenius bundles data and code from the projects below. JuziGenius's own
source code is proprietary and is not published; nothing here is covered by
whatever terms apply to that code. Each item keeps its own license.

These terms travel with the data to everyone who receives it. The two that
carry real conditions are the stroke data (Arphic Public License) and the
Tatoeba sentences (attribution required).

This file is published, together with the stroke data, at
<https://github.com/jwsanders76/juzigenius-data>.

---

## Stroke-order data — `stroke_data.json`

**Arphic Public License.** Full text in `ARPHICPL.TXT`, which accompanies the
data and is also served at <https://juzigenius.com/ARPHICPL.TXT>.

The file as JuziGenius uses it — a modified subset, described in its own
`_modifications` key — is freely available to anyone under the same license at
<https://github.com/jwsanders76/juzigenius-data>, as section 2(b) of the
license requires.

Vendored by `fetch_stroke_data.py` from the
[hanzi-writer-data](https://github.com/chanind/hanzi-writer-data) package, which
states:

> This data comes from the Make Me A Hanzi project, which extracted the data
> from fonts by Arphic Technology, a Taiwanese font forge that released their
> work under a permissive license in 1999.

Chain of provenance:

- Arphic Technology Co., Ltd. — AR PL UMing / AR PL KaitiM fonts, © 1999
- [Make Me a Hanzi](https://github.com/skishore/makemeahanzi) — extracted stroke
  graphics and medians from those fonts
- [hanzi-writer-data](https://github.com/chanind/hanzi-writer-data) — repackaged
  for Hanzi Writer

The Arphic Public License permits commercial use, copying and modification. It
requires that the license and copyright notices travel with the data, that
modifications be documented, and that derivative works of the data remain under
the same license. It applies to the **stroke data**, not to this application's
own source code.

> **Note:** `fetch_stroke_data.py` previously described this data as MIT. That
> was incorrect — the *Hanzi Writer library* is MIT, the *character data* is not.

## Hanzi Writer — `public/vendor/hanzi-writer.min.js`

**MIT License.** Copyright (c) 2014 David Chanin.
<https://github.com/chanind/hanzi-writer> — v3.5.0

> Permission is hereby granted, free of charge, to any person obtaining a copy of
> this software and associated documentation files (the "Software"), to deal in
> the Software without restriction, including without limitation the rights to
> use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
> of the Software, and to permit persons to whom the Software is furnished to do
> so, subject to the following conditions:
>
> The above copyright notice and this permission notice shall be included in all
> copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
> IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
> FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
> AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
> LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
> OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
> SOFTWARE.

## Kai typeface — `public/fonts/LXGWWenKai-Regular-subset.woff2`

[LXGW WenKai](https://github.com/lxgw/LxgwWenKai) v1.522, © LXGW and The Klee
Project Authors, under the SIL Open Font License 1.1 (text in
`public/fonts/LXGWWenKai-OFL.txt`). The file is a subset of the Regular weight,
cut to the characters in `stroke_data.json` with fontTools; it is used for the
Chinese on the victory card. The OFL permits bundling and subsetting but the
font may not be sold on its own.

---

## Example sentences — `tatoeba_sentences.csv`

**CC BY 2.0 FR** — <https://creativecommons.org/licenses/by/2.0/fr/>

Mandarin–English sentence pairs from the [Tatoeba Project](https://tatoeba.org),
obtained via the [manythings.org/anki](https://www.manythings.org/anki/) export
and filtered by `build_extra_sentences.py`.

**The sentences are modified.** They are not served exactly as Tatoeba
publishes them: traditional characters are converted to simplified, Taiwan
spellings are normalised, missing end punctuation is added, and about 5,800
pairs are corrected one by one -- a mistranslated English side, an unnatural or
mistaken Chinese side, or Taiwan vocabulary replaced with mainland usage. The
names Tom (汤姆) and Mary (玛丽), which about 3,360 of the sentences use, are
replaced throughout with Xiao Ming (小明) and Xiao Hong (小红), in the Chinese
and in the English. A few pairs are removed. Every hand correction is listed, with the reason for
it, in `tatoeba_corrections.tsv`; the source export is kept unmodified as
`tatoeba_cmn_eng_source.tsv`.

Tatoeba sentences are contributed by its members. Commercial use is permitted;
**attribution is required**, which is why Tatoeba is credited on the in-app
credits page and here.

`grammar_index.json` (built by `build_grammar_index.py`) repeats some of these
sentences, Chinese side only, as the examples a Character Bank or Word Bank
entry shows for a grammar pattern. It draws on nothing else, and the same
terms and the same credit cover it.

## Character dictionary — `hanzi_db.csv` → `master_dictionary.json`

Character definitions, radicals, stroke counts and frequency ranks. The
definition text follows the conventions of the **Unicode Han Database (Unihan)**
`kDefinition` field, distributed under the
[Unicode License](https://www.unicode.org/license.txt), which permits commercial
use with attribution.

© 1991–present Unicode, Inc. All rights reserved.

## Word list and glosses — `words_freq.json`

**License: CC BY-SA 4.0.** The whole file is distributed under the
[Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/),
because its HSK 4–6 glosses are adapted from CC-CEDICT. Commercial use is
permitted. The file carries this notice in its own `_license` key, so it travels
with the data.

Two sources:

- **HSK 1–3 entries (ranks 1–611)** — compiled for this project alongside the
  hand-written example sentences in `hsk_level1and2_words_with_sentences.csv` and
  `hsk_level3_words_with_sentences.csv`, and released under the same license so
  the file has a single set of terms.
- **HSK 4–6 entries (ranks 612+)** — word lists via
  [clem109/hsk-vocabulary](https://github.com/clem109/hsk-vocabulary), which takes
  them from [gigacool/hanyu-shuiping-kaoshi](https://github.com/gigacool/hanyu-shuiping-kaoshi),
  with English glosses from
  **[CC-CEDICT](https://www.mdbg.net/chinese/dictionary?page=cc-cedict)**
  (© MDBG and the CC-CEDICT contributors, CC BY-SA 4.0).

**How the CC-CEDICT origin was established (September 14, 2026).** Neither
upstream repository names a dictionary source, and both carry an MIT license that
covers their code — which could not have relicensed CC-CEDICT's text in any case.
The origin was confirmed from the data itself:

- The untouched upstream copy, `hsk_level4to6_vocab_source.json`, still contains
  CC-CEDICT's own annotations: classifier notes (`CL:個|个[gè]`), 13 `Taiwan pr.`
  pronunciation notes, 18 `variant of` and 9 `abbr. for` cross-references.
- Glosses match live CC-CEDICT entries sense for sense, in the same order — 一贯
  "consistent; constant; from start to finish; all along; persistent"; 重叠 "to
  overlap; to superimpose; to telescope; to run together; to duplicate; …".
  Sense lists like these do not arise independently.
- Where the wording differs slightly from today's CC-CEDICT (申请 "to apply for
  something; application (form etc)"), it matches an older release, consistent
  with a snapshot taken some years ago.

**Changes made**, as the license requires stating: classifier (`CL:`)
annotations were removed when the list was built (`build_words_freq.py`), and in
September 2026 373 glosses were corrected by hand — raw dictionary markup,
pronunciation notes, cross-references and self-referential senses removed, and a
few emptied glosses given new definitions (`backfill_word_meanings.py` lists every
change).

## Definitions — `glosses.json` and `cedict_source.txt.gz`

**License: CC BY-SA 4.0.** Both files are distributed under the
[Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/),
the license CC-CEDICT itself carries. **Commercial use is permitted.**
`glosses.json` holds the notice in its own `_license` key so the terms travel
with the data, exactly as `words_freq.json` does.

- **`cedict_source.txt.gz`** — the CC-CEDICT release as published by MDBG,
  kept gzipped and byte-for-byte unmodified so the checksum recorded in
  `cedict_source.LICENSE.txt` stays verifiable. Retrieved 2026-09-20;
  125,073 entries. Nothing reads it at runtime.
- **`glosses.json`** — built from it by `build_glosses.py`, and what the
  application loads.

- **`segment_lexicon.json`** — the list of words the victory card may box as
  one unit, built by `build_segment_lexicon.py`: the CC-CEDICT headwords of two
  to six characters that occur in this application's sentences, plus its own
  study lists, 11,156 words in all, each with a count taken from those
  sentences. It carries no definitions (those stay in `glosses.json`), but the
  selection of headwords is drawn from CC-CEDICT, so it is distributed under
  the same license and holds the notice in its own `_license` key. **Changes
  made:** reduced to the headwords described above; about 290 entries that
  are phrases rather than words removed by hand (`NEVER_WORDS` in the build
  script lists each one); headwords with no usable definition, and minor
  place names, removed; definitions and readings dropped; counts added.

- **`word_classes.json`** — which of the card's words are verbs
  (3,875) and which are adjectives (249), built by
  `build_word_classes.py` for the grammar notes. The verbs are the headwords
  CC-CEDICT defines as "to …", checked against how each word behaves in this
  application's sentences; the adjectives come from those sentences alone.
  Because the verb list is drawn from CC-CEDICT's definitions it is
  distributed under the same license and holds the notice in its own
  `_license` key. **Changes made:** reduced to a bare list of headwords; no
  definitions retained; about 180 headwords removed by hand
  (`NOT_VERBS` in the build script).

**Why this was added (September 20, 2026).** One English string per word had
to serve as both the practice prompt, which must be short, and the definition,
which must be complete. It cannot be both, and 一起 is the case that showed
it: the prompt read "in the same place" while the definition popup read
"together". `glosses.json` splits them — `primary` for prompts, `senses` for
the popup — and groups senses by reading, so 长 `cháng` "long" and 长 `zhǎng`
"to grow" are finally separate entries rather than one flattened string.

**Changes made**, as the license requires stating:

- Filtered to the ~18,100 headwords this application serves, out of 125,073
  (it was ~14,200 until the victory card's word list was added; see below).
- Characters that are only a traditional form left out (56 entries, such as
  礮, 絁 and 鑀, which CC-CEDICT lists in its simplified column too): this
  application stores and serves simplified text, so none can be looked up.
- Senses that are dictionary apparatus removed entirely: classifier notes
  (`CL:`), pronunciation notes (`Taiwan pr.`, `also pr.`, `colloquial pr.`),
  and `variant of` / `abbr. for` / `see` cross-references.
- The same notes removed where they ride *inside* an otherwise real sense —
  "light; ray (CL:道)", "to confess (Taiwan pr.)".
- Inline bracketed readings (`就是[jiu4 shi4]`) and traditional|simplified
  pairs (`個|个`) stripped from the remaining senses.
- Lexicographic shorthand spelled out: `sb` → someone, `sth` → something,
  and `derog.`, `coll.`, `lit.`, `fig.`, `esp.`, `usu.` written in full.
- Numeric tone digits rewritten as tone marks (`yi1 qi3` → `yī qǐ`), matching
  the convention used everywhere else in this project.
- **`primary` is frequently not CC-CEDICT's text at all.** Where this project
  already had a readable gloss of its own it is kept unchanged, which covers
  every HSK 1–3 entry and the 373 glosses corrected by hand in September 2026.
  A primary is taken from CC-CEDICT only for the 1,669 entries whose existing
  gloss was too long to serve as a prompt.

`test_glosses.py` asserts that no apparatus of any of these kinds survives
into a sense a learner can read.

**Share-alike attaches to this data file, not to the application.** Anyone may
copy, modify and redistribute `words_freq.json` under CC BY-SA 4.0, and adapted
versions of it must stay under the same license. Creative Commons licenses do not
propagate through linking the way the GPL does, so JuziGenius's own code is
unaffected, and charging for the app is permitted.

## HSK vocabulary lists

The HSK levels themselves are published by Hanban / Chinese Testing
International. The word lists are used here as reference data.

## HSK 3.0 character and word lists — `hsk3_characters.json`, `hsk3_words.json`

**License: CC BY-SA 4.0.** Which level of the nine-level HSK each of 3,088
characters belongs to, and the 1,200 of them the exam expects to be written by
hand, as set out in the syllabus Chinese Testing International published in
November 2025. The transcription is by Mani (krmanik),
<https://github.com/krmanik/HSK-3.0>, folder "New HSK (2025)", distributed under
the [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).
**Commercial use is permitted.** Provenance, the commit and a checksum are in
`hsk3_characters.LICENSE.txt`, and the file holds the notice in its own
`_license` key so the terms travel with the data.

**Changes made**, as the license requires stating: the source's
one-character-per-line text files were joined into one string per level by
`build_hsk3_characters.py`. No character was added, removed, reordered or moved
between levels.

**`hsk3_words.json`** is the same syllabus's word lists, 11,105 entries across
the seven levels, from the same source and commit, under the same license, and
copied unchanged — sense numbers, erhua spellings and parenthesised options as
the syllabus writes them. Nothing in JuziGenius reads it; it is vendored here
so that Vocabulary Builder's course is built from JuziGenius's inputs like
everything else it uses, and so that the licence record for both files is in
one place.

Share-alike attaches to these data files, not to the application, on the same
reasoning given for `glosses.json` above. It is kept as a file of its own, and
nothing from it is copied into `master_dictionary.json`, so that it attaches to
nothing else either; `test_hsk3.py` asserts that.

## Text-to-speech audio — removed

**Resolved: no third-party audio is distributed.** Speech is synthesized on the
user's own device by the browser's Web Speech API, using whichever Mandarin
voices that device has installed. Nothing about that passes through this
project, so no license attaches to it.

There was previously a pre-generated path: ~700 MB of MP3s produced by
`build_speech_audio.py` with [Piper](https://github.com/rhasspy/piper) (MIT) and
served from `/api/speech`. It was removed — from the app, the server and the
host — because Piper's *engine* is MIT but its *voice models* are licensed
separately, and both `zh_CN` voices used (`huayan`, `chaowen`) trace to the
[HuaYan_TTS](https://github.com/PlayVoice/HuaYan_TTS) dataset, whose license the
upstream Piper model card records as **"Unknown"**. The bundled
`model.onnx.json` files carry no license field either.

"Unknown" is not a grant of permission, and this app is heading for a paid tier.
`build_speech_audio.py` is kept, marked not-in-use, in case a properly-licensed
voice is adopted later; the serving code is in git history.

## Build-time tools

These generate vendored data but are not shipped or linked at runtime.

| Tool | License | Produces |
|---|---|---|
| [pypinyin](https://github.com/mozillazg/python-pinyin) | MIT | `pinyin_readings.json` |
| [opencc-python-reimplemented](https://github.com/yichen0831/opencc-python) | Apache 2.0 | `char_script_map.json` |

OpenCC conversion tables (`STCharacters.txt`, `TWVariants.txt`,
`HKVariants.txt`) are © [BYVoid](https://github.com/BYVoid/OpenCC) under the
Apache License 2.0.

---

## Corrections

Attribution errors here are bugs. If something is miscredited, mis-licensed, or
missing, please write to <support@juzigenius.com> or open an issue at
<https://github.com/jwsanders76/juzigenius-data/issues>.
