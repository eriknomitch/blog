---
title: "rsync remote directory"
date: 2019-05-21T13:26:00-05:00
draft: false
tags:
  - "unix"
  - "shell"
---

## Overview

<span style="font-size:larger;">
`rsync` is an excellent option to copy or synchronize a remote directory over `ssh`.
</span>

### Use Cases

* Transferring large directories since _**`rsync` will allow you to resume a transfer if it gets interrupted**_.
* Keeping directories in sync (periodically)

## Command

```Shell
$ rsync --recursive --info=progress2 --info=name0  --partial --rsh="ssh -q" [<user>@]<host>:<remote directory> <local directory>
```

<sub>
  See <a
    href="https://explainshell.com/explain?cmd=rsync+--recursive+--info%3Dprogress2+--info%3Dname0++--partial+--rsh%3D%22ssh+-q%22+erik%40remote-host%3A%2Fsrv%2Fdata%2Ftraining+training%2F"
    target="_BLANK"
  >
    Graphical Explanation
  </a>
</sub>

### Example Usage

**Important:** _Note the trailing `/` at the end of the local directory_

```Shell
$ mkdir training
$ rsync --recursive --info=progress2 --info=name0  --partial --rsh="ssh -q" erik@remote-host:/srv/data/training training/
```

## Scripting

Save this as `rsync-partial` somewhere in your `$PATH`.

```Shell
#!/bin/bash

_remote_host=$1
_remote_path=$2
_local_path=$3

# Ensure the local directory exists
test -d $3 || mkdir $3

rsync --recursive --info=progress2 --info=name0  --partial --rsh="ssh -q" $_remote_host:$_remote_path $_local_path/
```

### Example Usage

```Shell
$ rsync-partial erik@remote-host /srv/data/training training/
```
