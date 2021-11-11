# Zettelkasten with Zettel Cast Recording

***Currently refactoring. Do not use until v0.1+***

The `zet` command is a multicall bash script for managing one or more
Zettelkasten git repos with optional Zettel Cast live video recordings.

## Synopsis

In place of `zetid` the word `last` can be used instead as well as any path
to the `README.md` file or the “zet cast” video identifier (the id
or URL, if it has one).

```
usage
help
cast
import
delete
open
commit
video
urlencode
isosec
dir
create
edit
titles
last
text
title
body
query
ids
before
for
after
id
```

## Dependencies

The zet script requires Bash 4.0 (or above) and depends on the following
commands not normally installed by default:

-   yt
-   pandoc
-   curl
-   jq
-   auth

Environment

-   EDITOR
-   GITUSER
-   HELP_BROWSER

Completion

Add the following to bashrc to enable completion (replacing zet with
your multicall executable name):

    complete -C zet zet

Note that you will need one such complete line for every multicall
variation of this script:

    ln -s zet log
    complete -C log log

Filter Commands

True to the UNIX philosophy, most all commands can either take an
argument or will read from standard input recursively calling the same
command once for each line of input allowing commands to be called from
within Ed/Vim sessions as well as from the command line in pipeline
form.

Initial Setup

The zet command will create your public and private repository folders,
however to link it to github you will need to use `gh` or github.com to setup the github repository.
In your public and private folder run:
```
git init && gh repo create
```
Or you can use github.com to create the repositories.

Once setup make sure your upstream is set to your github repository for your commits to be pushed to github.
The zet commands will not indicate an issue with your repository as all messages are piped to /dev/null.
To set your upstream run:

```
git push -u <remote> <branch>
```



## Usage

```
```

## Commands

|  Command    | Summary                                                |
|    :-:      | -                                                      |
|  [usage]    | Display single line summary of all command usage |
|  [help]     | Display help information |

[usage]: #usage
[help]: #help

### `usage`

The `usage` command displays a summary of usage.

### `help`

The help command prints help information. If no argument is passed
displays general help information (main). Otherwise, the documentation
for the specific argument keyword is displayed, which usually
corresponds to a command name (but not necessarily). All documentation
is written in CommonMark (Markdown) and will displayed as Web page if
`pandoc` and `$HELP_BROWSER` are detected, otherwise, just the Markdown is
sent to `$PAGER` (default: `more`).

## Dependencies

Required:

* Bash 4+

Optional:

* `pandoc` - for rich help docs

## Justification

Bash is the dominate shell scripting language and the official default
Linux interactive shell, which reduces cognitive overhead; every command
line *is* a line of code that could be put into script as is. Bash
scripts are at the core of cloud, containers, and Kubernetes. Bash 4+
with its associative array support, powerful regular expressions, and
multiple ways of feeding data to loops easily covers the needs
previously requiring Python and Perl scripts. Bash scripts are also much
more powerful, safer, flexible, and performant than POSIX shell or Zsh.

## Caveats

* Use the official bash path: `#!/usr/bin/bash`
* Using `#!/usr/bin/env bash` introduces unnecessary risk
* Always set the acceptable `PATH` at beginning of script
* Always check script with [`shellcheck`] before releasing
* Always use `bc` for *any* floating point math

[`shellcheck`]: <https://www.shellcheck.net>

## Legal

Copyright 2021 Rob Muhlestein <rob@rwx.gg>  
Released under Apache-2.0 License  
Please mention <https://youtube.com/rwxrob>  

