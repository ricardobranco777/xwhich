![Build Status](https://github.com/ricardobranco777/xwhich/actions/workflows/ci.yml/badge.svg)

# xwhich
Enhanced which

## Usage

```
usage: ./xwhich [-h] [-a] [-i] [-P PATHS] [-s] [-x] [--version] command

positional arguments:
  command

options:
  -h, --help            show this help message and exit
  -a, --all             show all occurrences instead of the first
  -i, --insensitive     case insensitive search
  -P PATHS, --paths PATHS
                        restrict search to paths
  -x, --regex           search regular expression
  --version             show program's version number and exit
```

## Bugs / Limitations

- Windows is not supported unless you append `.exe` to the command and use `-i`

## Requirements

- Tested on Python 3.8+

## Examples

- List all commands that end with `conf`:

```
$ xwhich -a \*conf
/usr/sbin/resolvconf
/usr/sbin/nfsconf
/usr/sbin/postconf
/usr/bin/paperconf
/usr/bin/gpgconf
/usr/bin/x86_64-linux-gnu-pkgconf
/usr/bin/getconf
/usr/bin/pkgconf
/usr/bin/dconf
/usr/bin/debconf
/usr/bin/spd-conf
```

- List all commands that have at least 2 `x`'s:

```
$ xwhich -xa '.*x{2,}.*'
/usr/bin/min12xxw
/usr/bin/pbmtoibm23xx
/usr/bin/xxd
```

- List all commands that are `X` or `x`:

```
$ xwhich -i x
/usr/bin/X
```

- Restrict search to `/sbin:/usr/sbin`:

```
$ xwhich -P /sbin:/usr/sbin ls

```
