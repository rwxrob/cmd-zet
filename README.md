# Bash Command Template

This is a GitHub template repo that will be copied instead of forked
to create a new Bash command with a command something like this:

```
gh repo create rwxrob/mycmd -p rwxrob/bash-command-template
```

Obviously, not all of this is needed for
many Bash scripts, but anything with more than two subcommands will
benefit from the builtin tab completion, embedded Markdown help
documentation support, and included functions (`usage`, `_filter`,
`_filterbuf`, `_have`, etc.)

## Installation

It's usually easiest to install by cloning the repo and adding the full
path to this repo to your `PATH`. That way you can keep up with updates.

## Naming Conventions

* Name repo beginning with `cmd-` to help distinguish them
* Start command functions with `x_` to be completed
* Start command functions with `x__` to not be completed

## Usage

```
example
example usage
example help [<cmd>]
example foo [<arg>]
example bar [<arg>]
```

## Commands

|  Command    | Summary                                                |
|    :-:      | -                                                      |
|  [usage]    | Display single line summary of all command usage |
|  [help]     | Display help information |
|  [foo]      | Do the foo |
|  [bar]      | Do the bar |

[usage]: #usage
[help]: #help
[foo]: #foo
[bar]: #bar

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

## `foo`

The `foo` command foos.

## `bar`

The `bar` command bars.

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

