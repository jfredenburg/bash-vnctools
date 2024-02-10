# VNC tools
[![Makefile CI](https://github.com/ic-designer/bash-vnctools/actions/workflows/makefile.yml/badge.svg)](https://github.com/ic-designer/bash-vnctools/actions/workflows/makefile.yml)

## Installation

```bash
curl -sL https://github.com/ic-designer/bash-vnctools/archive/refs/tags/0.4.0.tar.gz | tar xz
make -C bash-vnctools-0.4.0 install
```

## Commands

### `vnctools-history`

Retrieves the last 1000 vnctools commands called by the current user.

```
usage: vnctools-history
```


### `vnctools-kill`

Connects to a remote server using ssh and kills the vnc desktop assigned to the display number.
This command also deletes the desktop lock files.

```
usage: vnctools-kill --username=<username> --hostname=<hostname>
                     --display=<display>

        --username=<username>       <username> provided to ssh
        --hostname=<hostname>       <hostname> provided to ssh
        --display=<display>         desktop <display> number
```


### `vnctools-list`

Connects to a remote server using ssh and lists the vnc desktops.

```
usage: vnctools-list --username=<username> --hostname=<hostname>

        --username=<username>       <username> provided to ssh
        --hostname=<hostname>       <hostname> provided to ssh
```


### `vnctools-open`

Opens the remote vnc desktop using an ssh tunnel.

```
usage: vnctools-open --username=<username> --hostname=<hostname>
                     --localport=<localport> --remoteport=<remoteport>
                     --display=<display>
                    [--realvnc | --screenshare]
                    [--sleep=<time>] [--x11args="<list of args>"]

        --username=<username>       <username> provided to ssh
        --hostname=<hostname>       <hostname> provided to ssh
        --localport=<localport>     <localport> number used during local forwarding port
        --remoteport=<remoteport>   <remoteport> number used during local forwarding port
        --display=<display>         desktop <display> number
        --realvnc                   open the desktop using realVNC app
        --screenshare               open the desktop using OSX screenshare app
        --sleep=<time>              <time> in seconds to wait between commands [Default: 4]
        --x11vnc="<list of args>"   <list of args> passed through to x11vnc [Default: ""]
```


### `vnctools-start`

Connects to a remote server using ssh and starts a new desktop.

```
usage: vnctools-start --username=<username> --hostname=<hostname>
                      --display=<display> --geometry=<geometry>

        --username=<username>       <username> provided to ssh
        --hostname=<hostname>       <hostname> provided to ssh
        --display=<display>         desktop <display> number
        --geometry=<geometry>       desktop <geometry> specified as <width>x<height>
```
