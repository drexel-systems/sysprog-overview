# sysprog.sh - assignement helper script

We provide `./scripts/sysprog.sh` as a helper to pull down files for each assignement. It can also help set up vscode with default build and debug targets.

This is not a required or critical part of your workflow - it is meant to be a helper only. You are free to use any method to set up your assignement repo. Failure of this script is not an excuse to not submit an assignment.

# command usage

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

You can run the script locally from the github location using curl:

