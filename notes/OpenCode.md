
Intro

Get started with opencode.

opencode is an AI coding agent built for the terminal.

opencode TUI with the opencode theme

Let’s get started.
Prerequisites

To use opencode, you’ll need:

    A modern terminal emulator like:
        WezTerm, cross-platform
        Alacritty, cross-platform
        Ghostty, Linux and macOS
        Kitty, Linux and macOS

    API keys for the LLM providers you want to use.

Install

The easiest way to install opencode is through the install script.
Terminal window

curl -fsSL https://opencode.ai/install | bash

You can also install it with the following:

    Using Node.js
        npm
        Bun
        pnpm
        Yarn
    Terminal window

    npm install -g opencode-ai

Using Homebrew on macOS and Linux
Terminal window

brew install sst/tap/opencode

Using Paru on Arch Linux
Terminal window

paru -S opencode-bin

Windows

Right now the automatic installation methods do not work properly on Windows. However you can grab the binary from the Releases.
Configure

With opencode you can use any LLM provider by configuring their API keys.

We recommend signing up for Claude Pro or Max, it’s the most cost-effective way to use opencode.

Once you’ve signed up, run opencode auth login and select Anthropic.
Terminal window

$ opencode auth login

┌  Add credential
│
◆  Select provider
│  ● Anthropic (recommended)
│  ○ OpenAI
│  ○ Google
│  ○ Amazon Bedrock
│  ○ Azure
│  ○ DeepSeek
│  ○ Groq
│  ...
└

Alternatively, you can select one of the other providers. Learn more.