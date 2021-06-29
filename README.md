# manop for macOS/Linux

## Overview

Manop is a simple Bash script that display a command description and options from Man page or help on macOS/Linux..

[Medium article](https://medium.com/mkdir-awesome/how-to-use-manop-to-print-only-selected-content-from-the-man-page-11309b9efa38)

## Requirements

UNIX-lie (Tested on Ubuntu and MacOS.)

## Installation

### Homebrew

If you installed [Homebrew](https://brew.sh/) on your macOS, you can run:

```sh
brew tap shinokada/manop && brew install manop
```

### Linux

#### [Awesome script package manager](https://github.com/shinokada/awesome)

```sh
awesome -i manop
```

#### Clone/Download

I keep manop in the `/home/shin/awesome` directory:

```sh
mkdir /home/your-username/awesome
cd /home/your-username/awesome
git clone https://github.com/shinokada/manop.git
```

Create the ~/bin directory:

```sh
mkdir ~/bin
```

Check if /home/your-username/bin in the PATH variable:

```sh
echo $PATH
/home/your-username/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
```

If not add the /home/your-username/bin directory to the ~/.bashrc file.

```sh
export PATH="/home/your-username/bin:$PATH"
```

Source the ~/.bashrc file and check it again:

```sh
source ~/.bashrc
echo $PATH
```

Add a symlink:

```sh
ln -s /home/your-username/awesome/manop/manop ~/bin/manop
```

Check if the symlink is working:

```sh
which manop
/home/your-username/bin/manop
manop -h
Name:
=====
manop
...
```

## Uninstallation

```sh
# brew
brew unistall manop
# awesome
awesome rm manop
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

## License

Please see license.
