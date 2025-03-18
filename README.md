# DDEV 'is-running' command 

## What is this?

Provides a simple ddeev host command to check if the ddev project is already running

the command `is-running` will print a notice and emit an exit code of 1 (failure) if the project is not running
this makes it great to use in shell script like githooks where you might need to check if ddev is running

## Installation

use `ddev add-on get wolffc/ddev-is-running` to get the latest version of the project

## Example usage

### Start the project if its not already running

```shell
ddev is-running || ddev start
```

### simple pre commit hook example

```shell

#!/usr/bin/env bash

# let this script fail on error
set -e

# check that ddev is running if not the script will fail
ddev is-running

# run a composer script to fire up your test pre commit 
ddev composer run tests:unit

```

