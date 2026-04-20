# java-setup

A reference guide for installing and configuring **Java 21 LTS** (Eclipse Temurin) on macOS using Homebrew.

## Contents

- [`java-setup-README.md`](./java-setup-README.md) — Step-by-step installation guide covering:
  - Installing Temurin 21 via Homebrew
  - Setting `JAVA_HOME` and `PATH` in `~/.zshrc`
  - Verifying the installation
  - Switching between multiple installed JDKs

## Quick Start

```zsh
brew install --cask temurin@21
```

Then add to `~/.zshrc`:

```zsh
export JAVA_HOME=$(/usr/libexec/java_home -v 21)
export PATH="$JAVA_HOME/bin:$PATH"
```

## License

[MIT](./LICENSE)
