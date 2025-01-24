# sysprog.sh - assignement helper script

We provide `./scripts/sysprog.sh` as a helper to pull down files for each assignement. It can also help set up vscode with default build and debug targets.

This is not a required or critical part of your workflow - it is meant to be a helper only. You are free to use any method to set up your assignement repo. Failure of this script is not an excuse to not submit an assignment.

# command usage

Run this from inside your personal cs503 git repo in the root folder. The pull command will place the assignement in it's own folder.

```
Usage: sysprog.sh <command> <command-argument>

Commands:
  list         List all assignments
  pull <name>  Pull the starter code and directions
  launch       Set up the local .vscode folder with necessary configuration
```

# using locally

Download `./scripts/sysprog.sh` and place in your local path (`/usr/local/bin` for example), or some location you would like to explicitly run it from.

# using remotely

You can run remotely with curl - here is the `list` example:

```sh
curl -sSL https://raw.githubusercontent.com/drexel-systems/sysprog-overview/main/scripts/sysprog.sh | sh -s -- list
```

Output:
```
Fetching assignements list curl -s  https://api.github.com/repos/drexel-systems/SysProg-Class/contents/assignments ...
    0-Warmup
    1-C-Refresher
    1a-C-Refresher-Part1
    2-StudentDB
```

Pull example:

```sh
curl -sSL https://raw.githubusercontent.com/drexel-systems/sysprog-overview/main/scripts/sysprog.sh | sh -s -- pull 2-StudentDB
```

# how to use launch config

Run `sysprog.sh launch` from the root of your personal cs503 git repo. It will create these files:

```sh
- .vscode/launch.json
- .vscode/tasks.json
```

These files create generic targets for `make` (for build) and `gdb` (for debug) in the integrated vscode debugger.

See `universal gdb debugging - how to use it` in [./universal-makefile/README>md](./universal-makefile/README>md) for detailed instructions.