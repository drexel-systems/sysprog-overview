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

# how to install

Option 1 - Copy the script out of [scripts/sysprog.sh](scripts/sysprog.sh) to anywhere in your path on your local system (like /usr/local/bin).

Option 2 - Curl it and run from anywhere - up to you where you place the script and how you access it

Example of option 1:

```sh
curl -sSL -o sysprog.sh https://raw.githubusercontent.com/drexel-systems/sysprog-overview/main/scripts/sysprog.sh
cp sysprog.sh /usr/local/bin
# or you could just run it like this from wherever you downloaded it:
./sysprog.sh
```

Example usages:

```sh
# excute
sysprog.sh list

# outputs:
Fetching assignements list curl -s  https://api.github.com/repos/drexel-systems/SysProg-Class/contents/assignments ...
    0-Warmup
    1-C-Refresher
    1a-C-Refresher-Part1
    2-StudentDB
```

```sh
# execute
sysprog.sh pull 2-StudentD

# outputs:
Fetching assignment 2-StudentDB from https://api.github.com/repos/drexel-systems/SysProg-Class/git/trees/main?recursive=1...
    Downloading file: 2-StudentDB/.gitignore
    Downloading file: 2-StudentDB/a2-directions.md
    Downloading file: 2-StudentDB/a2-questions.md
    Downloading file: 2-StudentDB/dblayout.png
    Downloading file: 2-StudentDB/readme.md
    Downloading file: 2-StudentDB/starter/db.h
    Downloading file: 2-StudentDB/starter/dblayout.png
    Downloading file: 2-StudentDB/starter/makefile
    Downloading file: 2-StudentDB/starter/sdbsc.c
    Downloading file: 2-StudentDB/starter/sdbsc.h
    Downloading file: 2-StudentDB/starter/test.sh
    Downloading file: 2-StudentDB/starter/testload.sh
Download completed for assignment: 2-StudentDB

========================================================================================
* Review 2-StudentDB/readme.md for instructions on how to complete the assignment 
*
* Happy coding! For assitance, please reach out via discord:                           
*
*            https://discord.com/channels/798568353689501758/1324393213850681394       
*
========================================================================================
```

# how to use launch config

Run `sysprog.sh launch` from the root of your personal cs503 git repo. It will create these files:

```sh
- .vscode/launch.json
- .vscode/tasks.json
```

These files create generic targets for `make` (for build) and `gdb` (for debug) in the integrated vscode debugger.

See `universal gdb debugging - how to use it` in [./universal-makefile/README>md](./universal-makefile/README>md) for detailed instructions.