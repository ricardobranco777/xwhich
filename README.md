# xwhich
Enhanced which

## Usage

```
usage: xwhich [-h] [-a] [-i] [-s] [-x] command

positional arguments:
  command

options:
  -h, --help         show this help message and exit
  -a, --all          Show all
  -i, --insensitive  Case insensitive
  -s, --shell        Check shell pattern
  -x, --regex        Check regular expression
```

## Notes

- The `-s` & `-x` are mutually exclusive.

## Bugs / Limitations

- Windows is not supported unless you append `.exe` to the command and use `-i`

## Examples

- List all commands that end with `conf`:

```
$ xwhich -sa \*conf
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
