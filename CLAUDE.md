# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a **Neovim configuration** based on [kickstart.nvim](https://github.com/nvim-lua/kickstart.nvim). It's a starting point for Neovim configuration that prioritizes being small, single-file, and completely documented.

## Key Architecture

- **Single-file configuration**: Primary configuration in `init.lua` (init.lua:1-1067)
- **Plugin management**: Uses `lazy.nvim` for plugin management (init.lua:248)
- **Modular plugins**: Additional plugins in `lua/kickstart/plugins/` directory
- **LSP integration**: Configured with `nvim-lspconfig`, `mason.nvim` for automatic LSP server installation
- **Completion**: Uses `blink.cmp` with `LuaSnip` for snippets

## Common Commands

### Plugin Management
- `:Lazy` - View current plugin status
- `:Lazy update` - Update plugins
- `:Mason` - View/install LSP servers and tools

### LSP and Development
- `:checkhealth` - Check Neovim health and configuration issues
- `:TSUpdate` - Update treesitter parsers

### Configuration
- Leader key: `<space>` (init.lua:90)
- Key mappings defined in init.lua starting at line 169

## Dependencies

External tools required:
- Basic utils: `git`, `make`, `unzip`, C Compiler (`gcc`)
- [ripgrep](https://github.com/BurntSushi/ripgrep), [fd-find](https://github.com/sharkdp/fd)
- Clipboard tool (platform-specific)
- Optional: Nerd Font (set `vim.g.have_nerd_font = true` in init.lua:94)

## Language Servers

Currently configured servers (init.lua:673-703):
- `lua_ls` - Lua language server
- `jdtls` - Java language server  
- `pyright` - Python language server

Additional servers can be added to the `servers` table in init.lua.

## Plugin Structure

- Core plugins defined in main `require('lazy').setup()` call (init.lua:248)
- Additional modular plugins loaded from `lua/kickstart/plugins/`:
  - `autopairs.lua` - Auto-pairing brackets/quotes
  - `gitsigns.lua` - Git integration
  - `indent_line.lua` - Indentation guides
  - `neo-tree.lua` - File explorer
  - `debug.lua` - Debug adapter protocol
  - `lint.lua` - Linting support

## Custom Configuration

User-specific settings at end of init.lua (init.lua:1045-1067):
- Tab settings: 2 spaces default, 4 spaces for HTML
- Custom keymaps for semicolon insertion and window resizing
- Case-insensitive search with smart case

## Important Notes

- This is NOT a Neovim distribution - it's a starting point for personal configuration
- Configuration is designed to be read and understood line-by-line
- Users should customize and extend based on their needs
- The goal is educational - understanding every line of configuration