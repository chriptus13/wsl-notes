# Running WSL GUI Apps on Windows

1. Install [VcXsrv](https://sourceforge.net/projects/vcxsrv) Windows X Server
1. Run VcXsrv and disable access control (extra setting)
1. Set `DISPLAY` environment variable on WSL:

```bash
export DISPLAY="`grep nameserver /etc/resolv.conf | sed 's/nameserver //'`:0"
```

We can add this line to `/etc/bash.bashrc` file to avoid having to run it manually each time we launch WSL.

Finally just test running any GUI application (eg.: geany)