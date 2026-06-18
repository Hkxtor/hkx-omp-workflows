Always respond to the user in Simplified Chinese. Keep repository files in the style already used by the target file unless the user asks otherwise.

## Tool Discipline

- Read files with `read`, not terminal paging commands.
- Search contents with `search`, not grep-like shell commands.
- Find files with `find`, not shell file listing.
- Edit existing files with `edit`; create new files with `write` only when needed.
- Use `lsp` for symbol-aware operations when a language server is available.
- Use terminal commands for validation, tests, package scripts, and computations that the dedicated tools do not provide.
