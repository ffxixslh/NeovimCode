# Repository Guidelines

## Project Structure & Module Organization

This repository is a VS Code Neovim configuration template inspired by LazyVim.
Keep source files small and configuration-focused:

- `config/vscode.lua`: Neovim-side mappings and VS Code action bridges.
- `config/settings.json`: VS Code settings, especially `VSpaceCode.whichkey`.
- `config/keybindings.json`: VS Code keybindings for modifier keys and special keys.
- `.vscode/extensions.json`: recommended VS Code extensions for this setup.
- `README.md`: user-facing setup notes and optional plugin guidance.

Do not add generated files, local machine paths, or editor cache directories.

## Build, Test, and Development Commands

There is no build step. Validate changes with focused checks:

- `rg "pattern"`: search keymaps, command IDs, and docs before editing.
- `git diff -- config/vscode.lua config/settings.json config/keybindings.json`: review scoped config changes.
- `nvim --headless -u NONE --cmd "lua vim.g.vscode=true" -c "luafile config/vscode.lua" "+qa"`: smoke-test the Lua template.

After changing live VS Code files, reload VS Code with `Developer: Reload Window`.

## Coding Style & Naming Conventions

Use two-space indentation in JSON/JSONC files. Comments are allowed in
`settings.json`, `keybindings.json`, and `.vscode/extensions.json`; keep them
short and directly tied to nearby bindings.

Keep leader-style mappings mirrored between `config/vscode.lua` and
`config/settings.json` when they should appear in WhichKey. Put modifier or
special-key bindings, such as `ctrl+up` or `alt+j`, in `config/keybindings.json`.
Use clear labels such as `Git Log`, `Next Buffer`, or `Fold All`.

## Testing Guidelines

No automated test framework or coverage target is configured. For JSONC changes,
verify the file still parses in VS Code. For Lua changes, run a Neovim headless
smoke test and inspect the changed mappings manually. For keybinding changes,
check the `when` clause carefully so shortcuts do not fire in terminals, quick
open, sidebars, or text inputs unless intended.

## Commit & Pull Request Guidelines

Follow the existing commit style: `feat: ...`, `fix: ...`, or `chore: ...`.
Keep commits narrow, for example `fix: restrict resize keybindings to editor`.

Pull requests should include a concise summary, affected config files, manual
verification steps, and any required VS Code extensions or optional command IDs.
Mention when Git integrations are plugin-specific; GitCharm commands are defaults
and may be replaced by commands from another Git extension.
