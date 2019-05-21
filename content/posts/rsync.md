---
title: "rsync"
date: 2019-05-21T13:26:00-05:00
draft: false
tags:
  - "unix"
  - "shell"
---

## Command

```Shell
rsync --partial --rsh="ssh -q" [<user>@]<host>:<remote directory> <local directory>
```

## Example

**Important:** _Note the trailing `/` at the end of the local directory_

```Shell
mkdir training
rsync --partial --rsh="ssh -q" erik@remote-host:/srv/data/training training/
```


