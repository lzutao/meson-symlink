# Install symlink script for Meson build system

This script helps you install a symlink when needed.  It should be portable
than shell script (Bash) and only need Python3.4+.  Windows users might need
administrator privileged when using this script.  Linux users should use
root privileged if wanted to install a symlink in system directories.

## How to use this

Place `symlink.py` in root directory of your project.
Use this snippet in `meson.build`:

```meson
meson.add_install_script('symlink.py', 'dash', 'sh', get_option('bindir'))
```

You could use this script standalone without Meson:

```r2
% python3 symlink.py -h
usage: symlink.py [-h] [-d] [-m MODE] source dest install_dir

example:
        symlink.py dash sh /bin

Install a symlink

positional arguments:
  source                target to link
  dest                  link name
  install_dir           installation directory

optional arguments:
  -h, --help            show this help message and exit
  -d, --isdir           dest is a directory
  -m MODE, --mode MODE  directory mode on creating if not exist
```
