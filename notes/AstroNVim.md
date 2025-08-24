
🚀 Getting Started

Tip

When getting started, please be sure to check out the Frequently Asked Questions!

AstroNvim Screenshot

AstroNvim is an aesthetically pleasing and feature-rich neovim config that is extensible and easy to use with a great set of plugins
⚡ Requirements

    Nerd Fonts (Optional with manual intervention: See Recipes/Customizing Icons) [1]
    Neovim v0.10+ (Not including nightly)
    Tree-sitter CLI (Note: This is only necessary if you want to use auto_install feature with Treesitter)
    A clipboard tool is necessary for the integration with the system clipboard (see :help clipboard-tool for supported solutions)
    Terminal with true color support (for the default theme, otherwise it is dependent on the theme you are using) [2]
    Optional Requirements:
        ripgrep - live grep file search (<Leader>fw)
        lazygit - git ui toggle terminal (<Leader>tl or <Leader>gg)
        go DiskUsage() - disk usage toggle terminal (<Leader>tu)
        bottom - process viewer toggle terminal (<Leader>tt)
        Python - python repl toggle terminal (<Leader>tp)
        Node - Node is needed for a lot of the LSPs, and for the node repl toggle terminal (<Leader>tn)

Note

[1] All downloadable Nerd Fonts contain icons which are used by AstroNvim. Install the Nerd Font of your choice to your system and in your terminal emulator settings, set its font face to that Nerd Font. If you are using AstroNvim on a remote system via SSH, you do not need to install the font on the remote system.

Note

[2] When using default theme: For MacOS, the default terminal does not have true color support. You will need to use iTerm2, Kitty, WezTerm, or another terminal emulator that has true color support.
🧰 Installation

Our configuration template is an easy way to going with AstroNvim. The template provides a directory structure with the required files in place. Within the files some indication, through commented out code, of how to configure the feature. Here are the instructions for installing this template:

Linux/Mac OS
Windows (PowerShell)

    Docker

    Make a backup of your current nvim config (if exists)
    Terminal window

    mv ~/.config/nvim ~/.config/nvim.bak

Clean neovim folders (Optional but recommended)
Terminal window

mv ~/.local/share/nvim ~/.local/share/nvim.bak
mv ~/.local/state/nvim ~/.local/state/nvim.bak
mv ~/.cache/nvim ~/.cache/nvim.bak

Clone the repository
Terminal window

git clone --depth 1 https://github.com/AstroNvim/template ~/.config/nvim
# remove template's git connection to set up your own later
rm -rf ~/.config/nvim/.git
nvim

📦 Setup

    Install LSP

    Enter :LspInstall followed by the name of the server you want to install

        Example: :LspInstall pyright

    Install language parser

    Enter :TSInstall followed by the name of the language you want to install

        Example: :TSInstall python

    Install Debugger

    Enter :DapInstall followed by the name of the debugger you want to install

        Example: :DapInstall python

    Manage plugins
        Run :Lazy check (<Leader>pu) to check for plugin updates
        Run :Lazy update (<Leader>pU) to apply any pending plugin updates
        Run :Lazy sync (<Leader>pS) to update and clean plugins
        Run :Lazy clean to remove any disabled or unused plugins

    Update Mason packages and plugins

    Run :AstroUpdate (<Leader>pa) to update both Neovim plugins and Mason packages

    Check AstroNvim version

    Run :AstroVersion to display the currently installed AstroNvim version

    Reload AstroNvim (EXPERIMENTAL)

    Run :AstroReload to reload the AstroNvim configuration and any new user configuration changes without restarting. This is currently an experimental feature and may lead to instability until the next restart.

✨ Features

    Common plugin specifications with AstroCommunity
    Statusline, Winbar, and Tabline with Heirline
    Plugin management with lazy.nvim
    Package management with mason.nvim
    File explorer with Neo-tree
    Autocompletion with Blink.cmp
    Git integration with Gitsigns
    Terminal with Toggleterm
    Fuzzy finding with snacks.picker
    Syntax highlighting with Treesitter
    Formatting and linting with none-ls
    Language Server Protocol with Native LSP

🔧 Configuration

To begin making customizations simply treat your nvim folder as your own Neovim configuration! This can be synced to a git repository to backup as well. AstroNvim is simply a plugin managed by the Lazy package manager that provides it’s own collection of plugins and their configurations.
🚀 The Starter Template

If you followed the instructions in this guide for installation, you are probably starting out with our template configuration. This comes with the following basic structure:

    Directory

~/.config/nvim/

README.md
init.lua bootstrap the lazy plugin manager
Directory
lua/

community.lua import AstroCommunity plugin specs
lazy_setup.lua configure and setup lazy.nvim
Directory
plugins/ configure plugins

astrocore.lua
astrolsp.lua
astroui.lua
mason.lua
none-ls.lua
treesitter.lua

    user.lua
    … add more files here as needed

            polish.lua file executed last with arbitrary Lua

Note

The list of files in the template may change over time as we fine tune what user’s want in the template, so the files above may be slightly different from the actual template.

At the top level is init.lua. This code bootstraps the configuration by installing lazy.nvim if it is not already installed and then calling lua/lazy_setup.lua to install and configure the AstroNvim and user plugins.

Looking a bit deeper, the plugins directory is where all plugins, except AstroNvim and AstroCommunity imports, are setup. The first three plugins are for the AstroNvim configuration. The next four plugins modify the configuration of a plugin that is part of AstroNvim (e.g.: treesitter.lua).

Each file in the plugins directory can specify the installation and configuration of one or more plugins. The template generally installs and configures a single plugin per lua file. Further, the name of the file generally matches the name of the plugin. The one exception is user.lua which has multiple plugins in it - but they could be split into separate files if you wish!

Be sure to check out the Configuration/Customizing Plugins page and the Lazy.nvim Documentation for more details in how to define and configure plugins using lazy.nvim.

There is nothing special about the template! It’s merely a quick way to get started, and, well, recommended to get you up and running quicker. Once you have a working configuration that may be the time when you start to move things around.

AstroNvim Template

NOTE: This is for AstroNvim v5+

A template for getting started with AstroNvim
🛠️ Installation
Make a backup of your current nvim and shared folder

mv ~/.config/nvim ~/.config/nvim.bak
mv ~/.local/share/nvim ~/.local/share/nvim.bak
mv ~/.local/state/nvim ~/.local/state/nvim.bak
mv ~/.cache/nvim ~/.cache/nvim.bak

Create a new user repository from this template

Press the "Use this template" button above to create a new repository to store your user configuration.

You can also just clone this repository directly if you do not want to track your user configuration in GitHub.
Clone the repository

git clone https://github.com/<your_user>/<your_repository> ~/.config/nvim

Start Neovim

nvim

