---
title: "rsync"
date: 2019-05-21T13:26:00-05:00
draft: false
tags:
  - "unix"
  - "shell"
---

## Overview

`rsync` is an excellent option to synchronize a remote and local directory over ssh.

### Use Cases

* Transferring large directories since **`rsync` will allow you to resume a transfer if it gets interrupted**.
* Keeping directories in sync (periodically)

---

### Command

```Shell
$ rsync --recursive --partial --rsh="ssh -q" [<user>@]<host>:<remote directory> <local directory>
```

### Example

**Important:** _Note the trailing `/` at the end of the local directory_

```Shell
$ mkdir training
$ rsync --recursive --partial --rsh="ssh -q" erik@remote-host:/srv/data/training training/
```
---

## Scripting

`rsync-partial`

```Shell
#!/bin/bash

_remote_host=$1
_remote_path=$2
_local_path=$3

# Ensure the local directory exists
test -d $3 || mkdir $3

rsync --recursive --partial --rsh="ssh -q" $_remote_host:$_remote_path $_local_path/
```

#### Example

```Shell
$ rsync-partial erik@remote-host /srv/data/training training/
```
