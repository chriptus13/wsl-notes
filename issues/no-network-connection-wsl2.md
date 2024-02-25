# No network connection WSL 2

Solved by:

```
=============================================================================
FIX WSL2 NETWORKING IN WINDOWS 10
=============================================================================
cmd as admin:
wsl --shutdown
netsh winsock reset
netsh int ip reset all
netsh winhttp reset proxy
ipconfig /flushdns

Windows Search > Network Reset

Restart Windows
-----------------------------------------------------------------------------
```

Or

```
# Fix network issues
# Delete auto-generated files
[root@PC-NAME user]# rm /etc/resolv.conf || true
[root@PC-NAME user]# rm /etc/wsl.conf || true

# Enable changing /etc/resolv.conf
# Enable extended attributes on Windows drives
[root@PC-NAME user]# cat <<EOF > /etc/wsl.conf
[network]
generateResolvConf = false

[automount]
enabled = true
options = "metadata"
mountFsTab = false
EOF

# Use google nameservers for DNS resolution
[root@PC-NAME user]# cat <<EOF > /etc/resolv.conf
nameserver 8.8.8.8
nameserver 8.8.4.4
EOF

Exit Linux WSL

cmd as admin:
wsl --shutdown
netsh winsock reset
netsh int ip reset all
netsh winhttp reset proxy
ipconfig /flushdns

Windows Search > Network Reset

Restart Windows
```

[Reference](https://github.com/microsoft/WSL/issues/5336#issuecomment-653881695)
