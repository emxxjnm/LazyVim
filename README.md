# LazyVim

Neovim config for the lazy powered by [💤 lazy.nvim](https://github.com/folke/lazy.nvim).

Can't decide between building a config from scratch or using one of the existing
Neovim **_distros_**?

With **LazyVim** you don't have to. Configuring **LazyVim** is
**exactly the same** as you would configure a config from scratch.
You can easily add new plugins, change the config for existing ones
or disable plugins.

![image](https://user-images.githubusercontent.com/292349/210136312-c211f781-6d51-46b0-a265-6098bdbb364d.png)

## 🚀 Getting Started

You can find a starter template for **LazyVim** [here](https://github.com/LazyVim/starter)

**TLDR:**

```lua
require("lazy").setup({
  spec = {
    -- import LazyVim plugins
    { "LazyVim/LazyVim", import = "lazyvim.plugins" },
    -- import/override with your plugins
    { import = "plugins" },
  },
  defaults = {
    lazy = true, -- every plugin is lazy-loaded by default
    version = "*", -- try installing the latest stable version for plugins that support semver
  },
})
```

## ✅ Todo

- [ ] documentation
- [x] treesitter auto-install seems broken. Switch to `ensure_installed` instead?
- [x] list all plugins in readme
- [ ] test all-the-things
- [x] auto-generate keymaps for README.md
- [x] auto-generate plugins for README.md

## ⌨️ Keymaps

<!-- keymaps:start -->

### General

| Key                  | Description                | Mode                       |
| -------------------- | -------------------------- | -------------------------- |
| `<C-h>`              | Go to left window          | **n**                      |
| `<C-j>`              | Go to lower window         | **n**                      |
| `<C-k>`              | Go to upper window         | **n**                      |
| `<C-l>`              | Go to right window         | **n**                      |
| `<C-Up>`             | Increase window height     | **n**                      |
| `<C-Down>`           | Decrease window height     | **n**                      |
| `<C-Left>`           | Decrease window width      | **n**                      |
| `<C-Right>`          | Increase window width      | **n**                      |
| `<A-j>`              | Move down                  | **n**, **v**, **i**        |
| `<A-k>`              | Move up                    | **n**, **v**, **i**        |
| `<S-h>`              | Prev buffer                | **n**                      |
| `<S-l>`              | Next buffer                | **n**                      |
| `[p`                 | Paste below                | **n**                      |
| `]p`                 | Paste above                | **n**                      |
| `<esc>`              | Escape and clear hlsearch  | **i**, **n**               |
| `n`                  | Next search result         | **n**, **x**, **o**        |
| `N`                  | Prev search result         | **n**, **x**, **o**        |
| `<C-s>`              | Save file                  | **i**, **v**, **n**, **s** |
| `<leader>l`          | Lazy                       | **n**                      |
| `<leader>fn`         | New File                   | **n**                      |
| `<leader>xl`         | Open Location List         | **n**                      |
| `<leader>xq`         | Open Quickfix List         | **n**                      |
| `<leader>tf`         | Toggle Format on Save      | **n**                      |
| `<leader>ts`         | Toggle Spelling            | **n**                      |
| `<leader>tw`         | Toggle Word Wrap           | **n**                      |
| `<leader>tn`         | Toggle Line Numbers        | **n**                      |
| `<leader>td`         | Toggle Diagnostics         | **n**                      |
| `<leader>tc`         | Toggle Conceal             | **n**                      |
| `<leader>gg`         | Lazygit (cwd)              | **n**                      |
| `<leader>gG`         | Lazygit (root dir)         | **n**                      |
| `<leader>qq`         | Quit all                   | **n**                      |
| `<leader>hl`         | Highlight Groups at cursor | **n**                      |
| `<leader>ot`         | Terminal (root dir)        | **n**                      |
| `<leader>oT`         | Terminal (cwd)             | **n**                      |
| `<esc><esc>`         | Enter Normal Mode          | **t**                      |
| `<leader>ww`         | other-window               | **n**                      |
| `<leader>wd`         | delete-window              | **n**                      |
| `<leader>w-`         | split-window-below         | **n**                      |
| `<leader>w\|`        | split-window-right         | **n**                      |
| `<leader><tab>l`     | Last                       | **n**                      |
| `<leader><tab>f`     | First                      | **n**                      |
| `<leader><tab><tab>` | New Tab                    | **n**                      |
| `<leader><tab>]`     | Next                       | **n**                      |
| `<leader><tab>d`     | Close                      | **n**                      |
| `<leader><tab>[`     | Previous                   | **n**                      |
| `<leader>b]`         | Next Buffer                | **n**                      |
| `<leader>bb`         | Switch to Other Buffer     | **n**                      |
| `<leader>b[`         | Previous Buffer            | **n**                      |
| `` <leader>`  ``     | Switch to Other Buffer     | **n**                      |

### LSP

| Key          | Description           | Mode         |
| ------------ | --------------------- | ------------ |
| `<leader>cd` | Line Diagnostics      | **n**        |
| `<leader>cl` | Lsp Info              | **n**        |
| `<leader>xd` | Telescope Diagnostics | **n**        |
| `gd`         | Goto Definition       | **n**        |
| `gr`         | References            | **n**        |
| `gD`         | Goto Declaration      | **n**        |
| `gI`         | Goto Implementation   | **n**        |
| `gt`         | Goto Type Definition  | **n**        |
| `K`          | Hover                 | **n**        |
| `gK`         | Signature Help        | **n**        |
| `[d`         | Next Diagnostic       | **n**        |
| `]d`         | Prev Diagnostic       | **n**        |
| `]e`         | Next Error            | **n**        |
| `[e`         | Prev Error            | **n**        |
| `]w`         | Next Warning          | **n**        |
| `[w`         | Prev Warning          | **n**        |
| `<leader>ca` | Code Action           | **n**, **v** |
| `<leader>cf` | Format Document       | **n**        |
| `<leader>cf` | Format Range          | **v**        |
| `<leader>cr` | Rename                | **n**        |

### Plugins

| Key               | Description                                                                                    | Mode  |
| ----------------- | ---------------------------------------------------------------------------------------------- | ----- |
| `<leader>cm`      | [mason.nvim](https://github.com/williamboman/mason.nvim.git) Mason                             | **n** |
| `<leader>bd`      | [mini.bufremove](https://github.com/echasnovski/mini.bufremove.git) Delete Buffer              | **n** |
| `<leader>bD`      | [mini.bufremove](https://github.com/echasnovski/mini.bufremove.git) Delete Buffer (Force)      | **n** |
| `<leader>ft`      | [neo-tree.nvim](https://github.com/nvim-neo-tree/neo-tree.nvim.git) NeoTree (root dir)         | **n** |
| `<leader>fT`      | [neo-tree.nvim](https://github.com/nvim-neo-tree/neo-tree.nvim.git) NeoTree (cwd)              | **n** |
| `<S-Enter>`       | [noice.nvim](https://github.com/folke/noice.nvim.git) Redirect Cmdline                         | **c** |
| `<leader>nl`      | [noice.nvim](https://github.com/folke/noice.nvim.git) Noice Last Message                       | **n** |
| `<leader>nh`      | [noice.nvim](https://github.com/folke/noice.nvim.git) Noice History                            | **n** |
| `<leader>na`      | [noice.nvim](https://github.com/folke/noice.nvim.git) Noice All                                | **n** |
| `<leader>nd`      | [nvim-notify](https://github.com/rcarriga/nvim-notify.git) Delete all Notifications            | **n** |
| `<leader>sr`      | [nvim-spectre](https://github.com/windwp/nvim-spectre.git) Replace in files (Spectre)          | **n** |
| `<leader>qs`      | [persistence.nvim](https://github.com/folke/persistence.nvim.git) Restore Session              | **n** |
| `<leader>ql`      | [persistence.nvim](https://github.com/folke/persistence.nvim.git) Restore Last Session         | **n** |
| `<leader>qd`      | [persistence.nvim](https://github.com/folke/persistence.nvim.git) Don't Save Current Session   | **n** |
| `<leader>/`       | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Find in Files (Grep)    | **n** |
| `<leader><space>` | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Find Files (root dir)   | **n** |
| `<leader>fb`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Buffers                 | **n** |
| `<leader>ff`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Find Files (root dir)   | **n** |
| `<leader>fF`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Find Files (cwd)        | **n** |
| `<leader>fr`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Recent                  | **n** |
| `<leader>gc`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) commits                 | **n** |
| `<leader>gs`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) status                  | **n** |
| `<leader>ha`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Auto Commands           | **n** |
| `<leader>hc`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Commands                | **n** |
| `<leader>hf`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) File Types              | **n** |
| `<leader>hh`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Help Pages              | **n** |
| `<leader>hk`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Key Maps                | **n** |
| `<leader>hm`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Man Pages               | **n** |
| `<leader>ho`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Options                 | **n** |
| `<leader>hs`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Search Highlight Groups | **n** |
| `<leader>ht`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Telescope               | **n** |
| `<leader>sb`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Buffer                  | **n** |
| `<leader>sc`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Command History         | **n** |
| `<leader>sg`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Grep (root dir)         | **n** |
| `<leader>sG`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Grep (cwd)              | **n** |
| `<leader>sm`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Jump to Mark            | **n** |
| `<leader>,`       | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Switch Buffer           | **n** |
| `<leader>:`       | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Command History         | **n** |
| `<leader>ss`      | [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim.git) Goto Symbol             | **n** |
| `]t`              | [todo-comments.nvim](https://github.com/folke/todo-comments.nvim.git) Next todo comment        | **n** |
| `[t`              | [todo-comments.nvim](https://github.com/folke/todo-comments.nvim.git) Previous todo comment    | **n** |
| `<leader>xt`      | [todo-comments.nvim](https://github.com/folke/todo-comments.nvim.git) Todo Trouble             | **n** |
| `<leader>xtt`     | [todo-comments.nvim](https://github.com/folke/todo-comments.nvim.git) Todo Trouble             | **n** |
| `<leader>xT`      | [todo-comments.nvim](https://github.com/folke/todo-comments.nvim.git) Todo Telescope           | **n** |
| `<leader>xx`      | [trouble.nvim](https://github.com/folke/trouble.nvim.git) Document Diagnostics (Trouble)       | **n** |
| `<leader>xX`      | [trouble.nvim](https://github.com/folke/trouble.nvim.git) Workspace Diagnostics (Trouble)      | **n** |
| `]]`              | [vim-illuminate](https://github.com/RRethy/vim-illuminate.git) Next Reference                  | **n** |
| `[[`              | [vim-illuminate](https://github.com/RRethy/vim-illuminate.git) Prev Reference                  | **n** |

<!-- keymaps:end -->

## 📦 Plugins

<!-- plugins:start -->

- [alpha-nvim](https://github.com/goolord/alpha-nvim)
- [catppuccin](https://github.com/catppuccin/nvim)
- [cmp-buffer](https://github.com/hrsh7th/cmp-buffer)
- [cmp-emoji](https://github.com/hrsh7th/cmp-emoji)
- [cmp-nvim-lsp](https://github.com/hrsh7th/cmp-nvim-lsp)
- [cmp-path](https://github.com/hrsh7th/cmp-path)
- [cmp_luasnip](https://github.com/saadparwaiz1/cmp_luasnip)
- [dressing.nvim](https://github.com/stevearc/dressing.nvim)
- [flit.nvim](https://github.com/ggandor/flit.nvim)
- [friendly-snippets](https://github.com/rafamadriz/friendly-snippets)
- [gitsigns.nvim](https://github.com/lewis6991/gitsigns.nvim)
- [indent-blankline.nvim](https://github.com/lukas-reineke/indent-blankline.nvim)
- [lazy.nvim](https://github.com/folke/lazy.nvim)
- [LazyVim](https://github.com/LazyVim/LazyVim)
- [leap.nvim](https://github.com/ggandor/leap.nvim)
- [lualine.nvim](https://github.com/nvim-lualine/lualine.nvim)
- [LuaSnip](https://github.com/L3MON4D3/LuaSnip)
- [mason-lspconfig.nvim](https://github.com/williamboman/mason-lspconfig.nvim)
- [mason.nvim](https://github.com/williamboman/mason.nvim)
- [mini.ai](https://github.com/echasnovski/mini.ai)
- [mini.bufremove](https://github.com/echasnovski/mini.bufremove)
- [mini.comment](https://github.com/echasnovski/mini.comment)
- [mini.indentscope](https://github.com/echasnovski/mini.indentscope)
- [mini.pairs](https://github.com/echasnovski/mini.pairs)
- [mini.surround](https://github.com/echasnovski/mini.surround)
- [neo-tree.nvim](https://github.com/nvim-neo-tree/neo-tree.nvim)
- [neoconf.nvim](https://github.com/folke/neoconf.nvim)
- [neodev.nvim](https://github.com/folke/neodev.nvim)
- [noice.nvim](https://github.com/folke/noice.nvim)
- [nui.nvim](https://github.com/MunifTanjim/nui.nvim)
- [null-ls.nvim](https://github.com/jose-elias-alvarez/null-ls.nvim)
- [nvim-bufferline.lua](https://github.com/akinsho/nvim-bufferline.lua)
- [nvim-cmp](https://github.com/hrsh7th/nvim-cmp)
- [nvim-lspconfig](https://github.com/neovim/nvim-lspconfig)
- [nvim-navic](https://github.com/SmiteshP/nvim-navic)
- [nvim-notify](https://github.com/rcarriga/nvim-notify)
- [nvim-spectre](https://github.com/windwp/nvim-spectre)
- [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter)
- [nvim-treesitter-textobjects](https://github.com/nvim-treesitter/nvim-treesitter-textobjects)
- [nvim-ts-context-commentstring](https://github.com/JoosepAlviste/nvim-ts-context-commentstring)
- [nvim-web-devicons](https://github.com/nvim-tree/nvim-web-devicons)
- [persistence.nvim](https://github.com/folke/persistence.nvim)
- [plenary.nvim](https://github.com/nvim-lua/plenary.nvim)
- [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim)
- [todo-comments.nvim](https://github.com/folke/todo-comments.nvim)
- [tokyonight.nvim](https://github.com/folke/tokyonight.nvim)
- [trouble.nvim](https://github.com/folke/trouble.nvim)
- [vim-illuminate](https://github.com/RRethy/vim-illuminate)
- [vim-startuptime](https://github.com/dstein64/vim-startuptime)
- [which-key.nvim](https://github.com/folke/which-key.nvim)

<!-- plugins:end -->
