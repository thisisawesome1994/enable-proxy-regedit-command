# enable-proxy-regedit-command

How to enable systemwide proxy support in windows 10?

Open command prompt or powershell as admin, and run the following commands:

reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings" /v ProxyEnable /t REG_DWORD /d 1
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings" /v ProxyServer /t REG_SZ /d proxy:port
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings" /v ProxyUser /t REG_SZ /d username
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Internet Settings" /v ProxyPass /t REG_SZ /d password
netsh winhttp import proxy source=ie

Beware:
Only use the first two and last command if your proxy has no password/username.
