# Page format

Every Mimirwiki page is available in five formats. The files in [docs/](docs/) are the Markdown format.

## Formats

| Format | How to get it | `Accept` header |
|---|---|---|
| HTML | `https://mimirwiki.com/wiki/json-rpc` | `text/html` |
| Markdown | add `.md` | `text/markdown` |
| Plain text | add `.txt` | `text/plain` |
| JSON | add `.json` | `application/json` |
| JSON-LD (schema.org) | add `.jsonld` | `application/ld+json` |

Korean pages have `/ko` before `/wiki`, for example `https://mimirwiki.com/ko/wiki/json-rpc.md`.

## Front matter

Each Markdown file starts with these fields.

| Field | Meaning |
|---|---|
| `title` | The name of the subject |
| `subtitle` | A one-line description |
| `canonical_url` | The address of the page on mimirwiki.com |
| `language` | `en` or `ko` |
| `page_class` | The kind of page |
| `revision_sha256` | The SHA-256 hash of this revision |
| `date_modified` | The date of the last change |
| `provenance` | How the page was written and whether an expert has reviewed it |
| `source_count` | The number of sources |
| `alternates` | The addresses of the other formats |
| `translations` | The addresses of the page in other languages |

## Sources

A number in square brackets, such as `[1]`, refers to the numbered list under "Sources" at the end of the page. Each source has its publisher, its address, the date it was checked and a tier.

| Tier | Kind of source |
|---|---|
| 1 | Government or public registry |
| 2 | Academic or news |
| 3 | Official site |

## Citing a page

Each page ends with a "Cite this page" line that includes the revision and the date.
