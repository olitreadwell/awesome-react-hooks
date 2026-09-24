# Contribution Guidelines

This list is checked by the
[awesome-list engine](https://github.com/olitreadwell/awesome-list-template),
and everything it expects of an entry is enforced by `make check`.

## Adding a project

- Open an [issue](https://github.com/olitreadwell/awesome-react-hooks/issues)
  first if you are unsure whether the project belongs here. The list is about
  React hooks: the libraries, tools, tutorials, and talks around them.
- One pull request per suggestion.
- Search the readme first. Duplicate entries are checked automatically.

## The shape of an entry

An entry is a bullet at the top level of a section:

```markdown
- [Project](https://example.com/) - What it is, in one sentence.
```

The description starts with a capital and ends with a period. The separator
between the link and the description is ` - `, not a colon.

A link on GitHub gets a star count and a last-push date appended when
`make stats` runs. Do not type those numbers yourself.

## Running the checks

```bash
uv sync --group dev
make hooks-install
make check
```

`make check` covers the entry grammar, the Contents list, the star and activity
snapshot, the exports, and the tests in `tests/test_readme.py`.
`make toc` rewrites the Contents list after you move a heading, and
`make stats` refreshes the stars and last-push dates for GitHub links.

## What a maintainer needs to decide

Nothing about an entry is mechanical except the grammar and the fetched numbers.
The words in a description belong to the person who suggested the project, so a
suggestion that adds a project has to bring its own description.
