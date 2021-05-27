# manop

## Overview

This script outputs a command description or an option description from the man or help page.

## Installation

### Homebrew

```sh
brew tap shinokada/manop
brew install manop
```

### Clone/Download

If you prefer clone/download, you clone/download this repo and make a symlink to your bin directory. Your bin directory needs to be in your PATH variable in your terminal configuration file, such as ~/.zshrc.

```sh
ln -sf ~/path/to/manop ~/bin/manop
```

## Usage

manop [ -t | -h | -v][ command name ][ command option ]
    -t | --trim    Trim spaces
    -v | --version Show version
    -h | --help    Help

### Examples

Shows wget -b option description:

```sh
manop wget -b
```

Shows the ls command description:

```sh
manop ls
```

Shows builtin commands description:

```sh
manop cd
```

Shows builtin cd -e option description:

```sh
manop cd -e
```

The outputs may have spaces. You can trim spaces:

```sh
manop grep -b
     -b, --byte-offset
             The offset in bytes of a matched pattern is displayed in front of
             the respective matched line.

manop -t grep -b
 -b, --byte-offset
 The offset in bytes of a matched pattern is displayed in front of
 the respective matched line.
```

To display builtin command help use help:

```sh
help cd
```

## Author

Shinichi Okada

## Licence

Please see license.txt.
