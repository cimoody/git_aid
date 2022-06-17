# DNS Errors 
Unfortunately I keep having them *#%!

### Latest commands that seemed to work for now
* In Administrator Command Prompt
  * `netsh command winsock reset catalog` - This will reset Winsock entries. **This command didn't work for me, so I skipped it
  * `netsh int ipv4 reset reset.log` - This command will reset IPv4 TCP/IP stack.
  * `netsh int ipv6 reset reset.log` - This will command reset the IPv6 TCP/IP stack. 
* Restart computer - from [DNS Media Disconnected](https://answers.microsoft.com/en-us/windows/forum/all/media-disconnected/c8179ed4-e3fa-46cc-b8d4-4b5923081c20)
