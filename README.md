# manop for macOS/Linux

## Overview

Manop outputs a command description or an option description from the man or help page.

[Medium article](https://medium.com/mkdir-awesome/how-to-use-manop-to-print-only-selected-content-from-the-man-page-11309b9efa38)

## Installation

### Homebrew

```sh
brew tap shinokada/manop && brew install manop
```

### Linux

I keep manop in the /home/shin/awesome directory:

```sh
mkdir /home/your-username/awesome
cd /home/your-username/awesome
git clone https://github.com/shinokada/manop.git
vim ~/.bashrc
```

Then add the PATH to the /home/your-username/bin directory in the ~/.bashrc file.

```sh
export PATH="/home/your-username/bin:$PATH"
```

Add a symlink:

```sh
ln -sf ~/path/to/manop ~/bin/manop
```

## Usage

manop [ -t | -h | -v][ command name ][ command option ]
    -t | --trim    Trim spaces
    -v | --version Show version
    -h | --help    Help

### Examples

Print `wget -b` option description:

```sh
manop wget -b
```

Print the `ls` command description:

```sh
manop ls
```

Print a builtin command description:

```sh
manop cd
```

Print the builtin cd -e option description:

```sh
manop cd -e
```

The outputs may have spaces. You can trim spaces using `-t` flag:

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
