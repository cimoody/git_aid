# Troubleshooting WSL

## No internet connection of WSL
https://stackoverflow.com/questions/62314789/no-internet-connection-on-wsl-ubuntu-windows-subsystem-for-linux
1. How to find out that there is no internet: `ping google.com` does not return anything.
2. Solution (https://github.com/microsoft/WSL/issues/3438#issuecomment-410518578):
a. Open Command Prompt as an Administrator and type these commands:
            netsh winsock reset 
            netsh int ip reset all
            netsh winhttp reset proxy
            ipconfig /flushdns
3. Reboot your machine.
