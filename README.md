# Haystack: File Search

Instant filename search for your whole Mac, modelled on voidtools **Everything**. Formerly
named MacFind. Haystack indexes every file and folder name on your disk (millions of entries in
about 20 seconds), keeps the index live as files change, and finds matches as you type. Tree mode
shows the size of every folder, and the Disk Map shows where your space goes.

**Privacy:** Haystack collects no data and makes no network connections. See [PRIVACY.md](PRIVACY.md).

**Manual:** [Haystack Manual.pdf](Haystack%20Manual.pdf), the full user manual.

## Getting started

On first launch Haystack asks for access to your disk: leave **Macintosh HD** selected and
click **Grant Access** (or choose a single folder to index only that folder). To include
private folders such as Mail and Safari data, click **Grant Full Disk Access…** in the status bar
and turn Haystack on in System Settings → Privacy & Security → Full Disk Access.

## Searching

Type to search. Return or ⌘O opens, ⌘R reveals in Finder, ⇧⌘C copies the full path, and you can
drag results out. Click a column header to sort. Search menu: Match Case (⌥⌘C), Match Path (⌥⌘P).
The **Tree** and **Disk Map** buttons at the top switch to folder sizes and the treemap.

Syntax (Everything's): space = AND, `|` = OR, `!` = NOT, `< >` groups, `"…"` exact phrase,
`*` and `?` wildcards match the whole name, a term containing `/` matches the full path, `~` = home.

| Modifier / function | Example |
|---|---|
| `case:` `path:` `regex:` `ww:` `startwith:` `endwith:` `exact:` `file:` `folder:` | `folder:exact:node_modules` |
| `ext:` | `ext:pdf;docx` |
| `size:` | `size:>10mb`, `size:1mb..5mb`, `size:huge` |
| `dm:` (date modified) | `dm:today`, `dm:last3days`, `dm:2026-10` |
| `len:` `parent:` `count:` | `parent:~/Downloads`, `count:20` |

## Command line and MCP

The app bundle includes `mf`, a command-line client (like Everything's `es.exe`):

```sh
sudo mkdir -p /usr/local/bin
sudo ln -s /Applications/Haystack.app/Contents/MacOS/mf /usr/local/bin/mf
mf -n 20 -s size -r ext:mov          # 20 largest .mov files
mf -l ~/Projects/ todo               # long listing, path match
mf --status
```

`mf --mcp` runs an MCP server on stdio with `search` and `status` tools, so AI assistants can
search your files by name. For Claude Code:

```sh
claude mcp add haystack -- /Applications/Haystack.app/Contents/MacOS/mf --mcp
```

## Support

Report problems or ask questions in [Issues](https://github.com/nullifyr/macfind/issues).
