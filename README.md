# vagrant-novnc

fluxbox on vagrant VM accessed through noVNC

## Quick start

Have VirtualBox and Vagrant installed already? Then clone this repo and `vagrant up` your VM! Point your browser to the VPN IP address on port 8080 and connect to the VNC server.

```
    $ git clone https://github.com/garcias/vagrant-novnc.git
    $ cd vagrant-novnc
    $ vagrant up
```

## What this does

Creates a local VM and provisions it with a VNC server you can access over WebSockets. Starts fluxbox desktop attached to `:99`.
