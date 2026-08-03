# 🚀LazyVim-Style Neovim Configuration for VS Code

Converted from [VimCode](https://github.com/wojukasz/VimCode).

## Required extensions:

- ["asvetliakov.vscode-neovim"](https://github.com/asvetliakov/vscode-neovim.git): Neovim integration
- ["VSpaceCode.whichkey"](https://github.com/VSpaceCode/vscode-which-key.git): Discoverable \<space\> menu

## Recommended extensions:

- ["RioNoir.gitcharm"](https://github.com/RioNoir/GitCharm): JetBrains-like Git management

## Git configuration

Git-related keymaps are optional examples. The default setup uses VS Code's
built-in Git commands together with GitCharm command IDs. If you use another Git
extension, replace the `command` values in `config/settings.json` and the
`action("...")` IDs in `config/vscode.lua` with commands provided by that
extension.

Current GitCharm defaults include:

- `<leader>gl` / `<space> g l`: `gitcharm.openLog`
- `<leader>gL` / `<space> g L`: `gitcharm.openLog`
- `<leader>gc` / `<space> g c`: `gitcharm.commit`
