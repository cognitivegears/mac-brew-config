# macOS Configuration with Homebrew

This repository contains a Brewfile that automates the setup of a macOS environment with a curated set of tools, applications, and utilities using [Homebrew](https://brew.sh).

## What's Included

The Brewfile includes:

- Command-line utilities (ripgrep, fzf, jq, etc.)
- Programming languages (Python, Go, Rust, Lua)
- Development tools (Git, Visual Studio Code, Neovim)
- Applications (Arc, Slack, Discord, etc.)
- Fonts and terminal emulators
- VS Code extensions
- Mac App Store applications

## Requirements

- macOS
- [Homebrew](https://brew.sh)
- For Mac App Store installations, you need to be signed in to the App Store

## Installation

### 1. Install Homebrew (if not already installed)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

After installation, follow the instructions displayed to add Homebrew to your PATH.

### 2. Clone this repository

```bash
git clone <repository-url>
cd <repository-directory>
```

### 3. Install everything from the Brewfile

```bash
brew bundle
```

This will install all packages, applications, and casks defined in the Brewfile. This might take some time depending on your internet connection and the number of packages to install.

### 4. Install VS Code extensions

VS Code extensions are included in the Brewfile and will be installed automatically if VS Code is already installed on your system.

## Usage

### Installing specific categories

If you want to install only a specific category:

- For command-line tools only:
  ```bash
  brew bundle --file=Brewfile
  ```

- For casks (applications) only:
  ```bash
  grep "^cask " Brewfile | sed 's/^cask "//' | sed 's/"$//' | xargs -I{} brew install --cask {}
  ```

### Updating installed packages

To update all packages installed by Homebrew:

```bash
brew update && brew upgrade && brew upgrade --cask
```

### Maintaining the Brewfile

To update the Brewfile with your current Homebrew setup:

```bash
brew bundle dump --force
```

This will overwrite the existing Brewfile with your current Homebrew installations.

## Customization

Feel free to customize the Brewfile to match your needs:

- Remove applications/packages you don't need
- Add new ones by editing the file directly
- Comment out lines by adding `#` at the beginning

## Troubleshooting

If you encounter issues:

1. Make sure Homebrew is up to date: `brew update`
2. Run `brew doctor` to check for problems
3. For failing casks, try installing them individually with `brew install --cask <name>`
4. For Mac App Store apps, ensure you're signed in to the App Store

## License

See the [LICENSE](LICENSE) file for details.
