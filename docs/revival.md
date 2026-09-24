# What this revival changed

`rehooks/awesome-react-hooks` last took a commit in July 2023. This fork runs
the list on the gate from
<https://github.com/olitreadwell/awesome-list-template>, pinned to engine
revision `0d13482`.

## The readme

- The heading read `# awesome-react-hooks`. It is `# Awesome React Hooks` now,
  which is what the linter reads as title case.
- `CONTRIBUTING.md` did not exist and the linter requires one. The new file
  describes the entry grammar this fork checks and how to run the gate.

## Entries

- 235 entries ran the description straight into the link, as in
  `- [crooks](url) A collection of unique React Hooks`. Each one took the same
  repair: insert ` - ` after the link. No word was added, removed, or moved.
- Three entries were missing the closing period on their description.
- `react-cool-inview` pointed at the `react-cool-onclickoutside` repository.
  The URL is the one the project actually lives at, and the star count and last
  push date came from `make stats` afterwards.
- `react-recipes` was listed twice, once in Catalogs and once in Packages, with
  the same URL and the same words. The Catalogs copy is gone.
- Two entries opened with an emoji shortcode, `:infinity:` and `:sunrise:`. The
  separator stripper eats a leading colon, so the checker read the first word as
  `infinity:` and called it lowercase. Both shortcodes are the emoji character
  now, which renders the same way. Nothing else about the lines changed.

## Left alone

- Every description from upstream is the words upstream wrote. The pass changed
  punctuation and link targets, nothing more.
- 26 entries are a bare link with no description. The gate warns about them and
  `tests/test_readme.py` holds that count. Writing those descriptions is not a
  revival.
- Thirteen spell-check warnings stay: `Github`, lowercase `react`, `WASM`, and
  `service worker`, each one a word the entries chose.
- The Indicative link inside the `react-indicative-hooks` description stays on
  http. https answers with a 530, and the engine checks the scheme of an entry's
  own URL rather than the links inside its description.

## Dead repositories

Ten entries link a GitHub repository that returns 404. The npm package still
ships for six of them (`@kevinwolf/formal`, `react-use-fetch-with-redux`,
`reaktion`, `resynced`, `use-videocard`, `use-reducer-with-effects`), and the
other four (`react-dom-status-hook`, `use-autocomplete`, `use-reactive-state`,
`use-scroller`) have no other home that could be confirmed in one pass. All ten
sit in `links.allowlist` so the gate stops asking for stars on a repository that
is gone. A maintainer should decide whether those entries point at npm or come
out of the list.

## Tooling

- `pyproject.toml` pins the engine, `Makefile` carries the engine targets, and
  `AGENTS.md` describes the layout.
- `github-stats.json` records stars and last push for the 216 GitHub entries
  that still resolve, and `exports/` holds the list as JSON, NDJSON, and CSV.
- `.githooks/pre-commit` and `.githooks/pre-push` run the gate. Install them
  with `make hooks-install`.
- `make check` covers the list rules, the Contents block, the stats snapshot,
  the exports, and the tests.
