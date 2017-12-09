<!-- {{{1 -->

    File        : README.md
    Maintainer  : Felix C. Stegerman <flx@obfusk.net>
    Date        : 2017-12-09

    Copyright   : Copyright (C) 2017  Felix C. Stegerman
    Version     : v0.1.1

<!-- }}}1 -->

[![PyPI Version](https://img.shields.io/pypi/v/mmm.svg)](https://pypi.python.org/pypi/mmm)
[![Build Status](https://travis-ci.org/obfusk/m.svg?branch=master)](https://travis-ci.org/obfusk/m)

## Description

m - minimalistic media manager

m keeps track of which files you've played (or are still playing) and
thus allows you to easily continue playing the next file (using vlc).

* Supports importing existing playing/watched data from Kodi.
* Stores its data in JSON files (one per directory) in `~/.obfusk-m`;
  you can put this directory in git if you want a changelog :)

NB: extracting the timestamp from the vlc config is a little hacky :(

## Examples

```bash
$ cd /some/media/dir
$ m ls    # list files ([*] = skip, [x] = done, [>] = playing, [ ] = new)
[x] Something - 01.mkv
[x] Something - 02.mkv
[x] Something - 03.mkv
[x] Something - 04.mkv
[x] Something - 05.mkv
[x] Something - 06.mkv
[>] Something - 07.mkv 0:04:04
[ ] Something - 08.mkv
[ ] Something - 09.mkv
$ m next  # plays current/next episode (i.e. #7) w/ vlc
```

```bash
$ m ld    # list dirs (shows #playing, #new for indexed subdirectories)
(   2!) Dir A
(     ) Dir B
(1> 0!) Dir C
(   0!) Dir D
```

Commands include: `list`/`ls`, `list-dirs`/`ld`, `list-all`/`la`,
`next`, `play FILE`, `mark FILE`, `unmark FILE`, `skip FILE`, `index`.

See also the tests in the source code for more examples.

## Installing

You can just put `m.py` somewhere on your `$PATH` (in e.g. `~/bin`; I
suggest calling it `m`, but you're free to choose another name).

Alternatively, you can use pip:

```bash
$ pip3 install --user mmm   # for Debian; on other OS's you may need
                            # pip instead of pip3 and/or no --user
```

## TODO

* `ack TODO`
* more file extensions!
* kodi db export/sync?
* sign pypi package?

## License

[GPLv3+](https://www.gnu.org/licenses/gpl-3.0.html).

<!-- vim: set tw=70 sw=2 sts=2 et fdm=marker : -->
