# Java 21 Installation & Configuration

## Overview

Upgraded the default Java runtime on macOS from JDK 13.0.1 to **Eclipse Temurin 21 (LTS)**.

## Prerequisites

- macOS with [Homebrew](https://brew.sh) installed
- `sudo` access (required by the Temurin installer)

## Installation Steps

### 1. Install Temurin 21 via Homebrew

```zsh
brew install --cask temurin@21
```

This installs Eclipse Temurin 21.0.10 (~200 MB) to:

```
/Library/Java/JavaVirtualMachines/temurin-21.jdk/
```

### 2. Configure JAVA_HOME and PATH

Append the following to `~/.zshrc`:

```zsh
# Java - set to LTS (21)
export JAVA_HOME=$(/usr/libexec/java_home -v 21)
export PATH="$JAVA_HOME/bin:$PATH"
```

### 3. Apply the Changes

```zsh
source ~/.zshrc
```

## Verification

### Check Java version

```zsh
java -version
# openjdk version "21.0.10" 2026-01-20 LTS
# OpenJDK Runtime Environment Temurin-21.0.10+7 (build 21.0.10+7-LTS)
# OpenJDK 64-Bit Server VM Temurin-21.0.10+7 (build 21.0.10+7-LTS, mixed mode, sharing)
```

### Check JAVA_HOME

```zsh
echo $JAVA_HOME
# /Library/Java/JavaVirtualMachines/temurin-21.jdk/Contents/Home
```

### Hello World smoke test

```zsh
# Compile
javac HelloWorld.java

# Run
java HelloWorld
# Hello, World!
```

## Installed JDKs on This Machine

| Version | Vendor | Path |
|---------|--------|------|
| 21.0.10 | Eclipse Temurin *(active)* | `/Library/Java/JavaVirtualMachines/temurin-21.jdk` |
| 13.0.1 | Oracle | `/Library/Java/JavaVirtualMachines/jdk-13.0.1.jdk` |
| 11.0.16.1 | Microsoft | `/Library/Java/JavaVirtualMachines/microsoft-11.jdk` |
| 11.0.10 | Oracle | `/Library/Java/JavaVirtualMachines/jdk-11.0.10.jdk` |
| 11.0.8 | Amazon Corretto | `/Library/Java/JavaVirtualMachines/amazon-corretto-11.jdk` |
| 8.0.392 | Amazon Corretto | `/Library/Java/JavaVirtualMachines/amazon-corretto-8.jdk` |
| 8.0.302 | Eclipse Temurin | `/Library/Java/JavaVirtualMachines/temurin-8.jdk` |

## Switching Java Versions

To temporarily switch to a different JDK in the current shell session:

```zsh
export JAVA_HOME=$(/usr/libexec/java_home -v 11)
export PATH="$JAVA_HOME/bin:$PATH"
java -version
```

To list all installed JDKs:

```zsh
/usr/libexec/java_home -V
```
