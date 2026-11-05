# Haystack Privacy Policy

_Last updated: November 5, 2026_

Haystack: File Search (formerly MacFind) does not collect, store, transmit or share any personal data.

- Haystack builds an index of file and folder **names**, sizes and dates on the disk you choose.
  It never reads file contents.
- The index is stored only on your Mac. Nothing leaves your Mac.
- Haystack makes no network connections and contains no analytics, advertising or tracking code.
- The `mf` command-line tool and its MCP mode only talk to the Haystack app running on the same
  Mac, through a private local socket. If you connect an AI assistant to Haystack via MCP, the
  search results you request (names, paths, sizes and dates) are passed to that assistant, under
  that assistant's own privacy terms.

To remove all Haystack data, delete the app, then delete the folder
`~/Library/Group Containers/BVM4W42ZKJ.com.macfind`, which holds the index.

Questions: open an issue at https://github.com/nullifyr/macfind/issues.
